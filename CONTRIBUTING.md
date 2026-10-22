# Contributing

Keep changes focused on this console learning project. Prefer a small, readable fix over adding a framework or database without a specific requirement.

## Development and verification

Follow the README's proposed compile/run commands with the actual formatter JAR. Report the JDK, classpath, commands and results actually checked. No automated test suite is supplied; add a focused regression check for changed non-trivial logic where practical.

Useful scenarios include an empty catalogue, available-only output when all books are borrowed, missing IDs, repeated borrow/return, the eleventh insertion triggering array growth, invalid menu text, oversized integers, end-of-input and long table cells.

Preserve sequential IDs and the meaning of availability unless intentionally changing the interface. A future persistence feature needs an explicit storage/recovery design; it should not be implied by table output alone.

## Pull requests

Describe the problem, focused change, verification and remaining gaps. Keep generated class files, private records and unrelated IDE changes out of commits. Follow [SECURITY.md](SECURITY.md) for sensitive concerns.
