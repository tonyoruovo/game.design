For an open source Java library managed with Maven, the gold standard is the **Conventional Commits** specification. It is widely recognized, machine-readable, and integrates perfectly with automated release tools like semantic-release or JReleaser.

### 1. The Standard Format

Each commit message should follow this structure:

```text
<type>(<scope>): <description>

[optional body]

[optional footer(s)]

```

---

### 2. Common Types for Java/Maven Projects

Using specific types helps you automatically generate a `CHANGELOG.md`.

* **feat**: A new feature (e.g., adding a new API method).
* **fix**: A bug fix (e.g., fixing a `NullPointerException`).
* **docs**: Documentation only changes (Javadoc, README).
* **style**: Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons).
* **refactor**: A code change that neither fixes a bug nor adds a feature.
* **perf**: A code change that improves performance.
* **test**: Adding missing tests or correcting existing tests.
* **build**: Changes that affect the build system or external dependencies (e.g., updating `pom.xml`, Maven plugins).
* **ci**: Changes to CI configuration files and scripts (e.g., GitHub Actions, Jenkins).
* **chore**: Other changes that don't modify src or test files.

---

### 3. Examples in Context

| Type | Example Message |
| --- | --- |
| **Feature** | `feat(core): add support for JSON serialization` |
| **Fix** | `fix(io): resolve thread-safety issue in FileScanner` |
| **Build** | `build(deps): bump jackson-databind from 2.15.0 to 2.15.2` |
| **Docs** | `docs(readme): clarify installation steps for Maven Wrapper` |
| **Breaking Change** | `feat(api)!: remove deprecated validate() method` |

> **Note on Breaking Changes:** The `!` after the type/scope or the `BREAKING CHANGE:` footer signals a major version bump () in Semantic Versioning.

---

### 4. Why this works for Open Source

1. **Automation:** You can use the `git-commit-id-plugin` in your `pom.xml` to bake commit info into your JAR.
2. **Semantic Versioning:** Tools can read your commits to decide if the next release should be a **patch**, **minor**, or **major** update.
3. **Contributor Clarity:** It makes it easy for outside contributors to understand the history of the project without reading every line of code.

### 5. Recommended Scopes for Java

In Java projects, the "scope" is usually the **sub-module** name or the **primary package** being modified:

* `feat(security): ...`
* `fix(parser): ...`
* `build(parent): ...`

---
