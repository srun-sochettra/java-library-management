# Java Library Management

**A console catalogue for adding, browsing, borrowing and returning books.**

A Java coursework project by **Srun Sochettra**, exploring object-oriented modelling, input handling and a manually resized array. Books and authors are displayed in terminal tables using the bundled text-table-formatter dependency.

This is an in-memory learning application, not a database-backed library service. Records disappear when the process exits.

## What you can do

Start by entering a library name and address, then choose a menu option:

| Option | Action |
| --- | --- |
| `1` | Add a book with its title, author, author activity text and publication year |
| `2` | Show all books |
| `3` | Show available books only |
| `4` | Borrow a book by ID |
| `5` | Return a book by ID |
| `6` | Exit |

New books receive sequential IDs starting at 1 and begin available. Missing IDs and duplicate borrow/return actions produce messages without changing availability. There are no borrower accounts, due dates, fines, editing or deletion features.

## Run locally

The original README recommends **JDK 21**. The IntelliJ module inherits its JDK rather than pinning one; this refresh does not establish a minimum supported version.

The repository inventory lists `lib/text-table-formatter-1.2.4.jar`, and the IntelliJ module references that path. The binary is excluded from the text export, so use the original checkout and confirm the JAR exists. Its contents and compatibility were not tested here.

### Windows PowerShell

Suggested commands from the repository root:

```powershell
javac -encoding UTF-8 -cp "lib/text-table-formatter-1.2.4.jar" -d out src/Main.java
java -cp "out;lib/text-table-formatter-1.2.4.jar" Main
```

### POSIX shell

```sh
javac -encoding UTF-8 -cp "lib/text-table-formatter-1.2.4.jar" -d out src/Main.java
java -cp "out:lib/text-table-formatter-1.2.4.jar" Main
```

These are proposed local commands, not commands executed during this refresh. The runtime classpath separator differs between the two shells/platforms. Alternatively, open the project in IntelliJ IDEA, review its JDK and library configuration, and run Main.

No database, API key or environment file is used by the supplied source. There is no Maven or Gradle build configuration in the export.

## Implementation

All application classes are in [src/Main.java](src/Main.java):

| Class | Responsibility |
| --- | --- |
| `Author` | Author name and free-text activity period |
| `Book` | ID, title, author, publication year and availability |
| `InputUtil` | Menu parsing, positive integers and non-empty text |
| `Library` | Catalogue storage, lookup, table output and borrow/return state |
| `Main` | Setup prompts and menu loop |

The catalogue starts with ten array slots and doubles capacity when full. Lookup scans stored entries by ID. This demonstrates array growth, not unlimited storage.

Setup displays a timestamp using `Asia/Phnom_Penh`. It is a setup message, not a loan timestamp or audit log. Table columns have configured widths and cropping, so long text may be shortened in the display.

## Input and scope limitations

- Menu choices are restricted to 1–6; numeric fields accept positive integer text.
- Very large digit strings can still cause integer parsing to fail. End-of-input is not handled as a graceful exit.
- Publication year is checked only as a positive integer, not against a calendar range. Author activity is non-empty text, not a validated date interval.
- Duplicate titles/authors are not rejected.
- Borrow/return changes a boolean flag. It is not a database transaction or a borrower-history system.
- No persistent storage, authentication or automated test suite is supplied.

These are source observations, not repairs included in this package. No compilation, dependency loading, application execution or behavioural testing was performed during the documentation refresh.

## Contributing and security

See [CONTRIBUTING.md](CONTRIBUTING.md) and [SECURITY.md](SECURITY.md). Suggested repository metadata and application instructions for this documentation overlay are in [the refresh notes](docs/repository-refresh.md).

## Licence

No project licence file is included in the supplied export. This refresh does not assign one or establish redistribution rights for the bundled third-party JAR. Confirm project and dependency permissions separately.
