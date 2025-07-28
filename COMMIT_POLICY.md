# Commit Message Policy and Prefixes

Commit prefixes improve clarity and traceability, allowing any team member to quickly identify the nature and intention of each change.  
Below are the standard categories and how/when to use each one.

---

## [SAFETY] — Safety or Reliability Improvement

**Use this prefix when the change is critical for device safety, recovery, robustness, or prevents situations that could leave the device in an unsafe or unreachable state.**

**Examples:**
- Adding a watchdog timer or restart logic for connectivity loss.
- Ensuring device always recovers from crash or disconnect.
- Any fix that prevents data loss, bricking, or unrecoverable offline state.

**Commit Example:**
```
[SAFETY] Add watchdog auto-restart after WiFi offline timeout
```

---

## [BUGFIX] — Fixes a Bug or Malfunction

**Use for all corrections of defects, logical errors, or unexpected behaviors.**

**Examples:**
- Fixes to incorrect device outputs, sensor readings, or protocol parsing.
- Corrections for crashes, infinite loops, or stack overflows.
- Patch to eliminate memory leaks.

**Commit Example:**
```
[BUGFIX] Fix buffer overflow in MQTT payload parser
```

---

## [FEATURE] — New Feature or Capability

**Use when introducing new user-facing functionality, protocol, or options.**

**Examples:**
- Adding new MQTT command types, sensor support, or configuration options.
- Integrating a new hardware component.
- Enabling additional user controls or reporting.

**Commit Example:**
```
[FEATURE] Support for OTA firmware upgrade via MQTT
```

---

## [REFACTOR] — Code Structure or Cleanup

**Use when changing code layout, function names, splitting files, or improving code style, _but without altering external behavior_.**

**Examples:**
- Restructuring functions for clarity or maintainability.
- Moving code between files, or renaming identifiers.
- Removing unused variables, comments, or dead code.

**Commit Example:**
```
[REFACTOR] Split device state logic into separate modules
```

---

## [DOC] — Documentation Only

**Use when the commit affects only comments, markdown files, diagrams, or code explanations (not the code logic itself).**

**Examples:**
- Adding/changing README or inline code documentation.
- Adding usage or API documentation.
- Updating configuration or deployment instructions.

**Commit Example:**
```
[DOC] Document WiFi recovery and auto-restart logic
```

---

## [CONFIG] — Project or Build Configuration

**Use for changes to build scripts, dependencies, project files, or CI/CD settings.**

**Examples:**
- Updates to `platformio.ini`, Dockerfile, or CI/CD scripts.
- Changes to board or hardware target settings.
- Pin mapping or hardware abstraction changes.

**Commit Example:**
```
[CONFIG] Update platformio.ini for ESP32 release target
```

---

## Best Practices for Commit Messages

- **Use only one prefix per commit** (unless absolutely necessary).
- **Start with a capital letter** and use the imperative mood (e.g., "Add", "Fix", "Refactor").
- **Explain the reason** and/or consequence in the description/body if not obvious.
- **Group related changes** together; avoid large, unrelated commits.
- If the change is **critical and must not be removed**, say so clearly in the commit body (e.g., "DO NOT REMOVE: Required for remote device recovery").

---

## Examples for Your Project

- `[SAFETY] Add periodic WiFi reconnect and offline watchdog auto-restart`
- `[BUGFIX] Fix JSON parsing for CONFIG_SERIAL_NUMBER_ENUM`
- `[FEATURE] Implement new pairing command via MQTT`
- `[DOC] Add commit prefix policy to developer documentation`
- `[REFACTOR] Clean up command switch statement and helper functions`

---

## When in Doubt

If you are unsure, **prefer being conservative** — mark as `[SAFETY]` when it could impact field reliability, `[BUGFIX]` when it solves a defect, and `[FEATURE]` when it brings something new to the user or device capabilities.

---

**Document History**
- v1.0 — 2024-07-26 — Initial policy by Felipe Vargas / SmartCloudAge
