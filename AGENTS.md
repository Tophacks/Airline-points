# AGENTS.md

## Cursor Cloud specific instructions

This is a simple Java Swing desktop application (Airline Points Tracker) with no build system, no external dependencies, and no automated tests.

### Compile & Run

```bash
# Compile (from repo root)
javac -d out NatePowellAirlinePoints.java AirlinePointsUI.java

# Run (requires DISPLAY, e.g. :1 via Xvfb)
DISPLAY=:1 java -cp out nate.powell.airline.points.AirlinePointsUI
```

### Key caveats

- **No build tool**: There is no Maven/Gradle/Ant. Use `javac`/`java` directly.
- **Swing GUI**: The app requires a graphical display. In the cloud VM, `DISPLAY=:1` is already set via the existing X server.
- **No tests**: The project has no test framework or test files. Verification is manual only — launch the app and interact with the GUI.
- **Package structure**: Source files declare `package nate.powell.airline.points;` but live at the repo root (not in a matching directory tree). Use `javac -d out` to produce the correct package directory under `out/`.
- **No lint**: There is no linter configured. You can use `javac` compilation as a basic correctness check.
