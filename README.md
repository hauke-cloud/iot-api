<!-- llm-readme-management spec=1 commit=6a8264c6eabc2bb378073bb6bd08f0624ea60af2 template=terraform model=qwen3.6-35b-a3b digest=f68682b55584 generated=2026-09-08T20:39:01Z -->
<a href="https://hauke.cloud" target="_blank"><img src="https://img.shields.io/badge/home-hauke.cloud-brightgreen" alt="hauke.cloud" style="display: block;" /></a>
<a href="https://github.com/hauke-cloud" target="_blank"><img src="https://img.shields.io/badge/github-hauke.cloud-blue" alt="hauke.cloud Github Organisation" style="display: block;" /></a>
<a href="https://github.com/hauke-cloud/llm-readme-management" target="_blank"><img src="https://img.shields.io/badge/template-terraform-orange" alt="Repository type - terraform" style="display: block;" /></a>


# Template Repository


<img src="https://raw.githubusercontent.com/hauke-cloud/.github/main/resources/img/organisation-logo-small.png" alt="hauke.cloud logo" width="109" height="123" align="right">


<llm header hint="Say whether this is a reusable module or a root module that owns real state.">

This repository provides a reusable Go module that defines shared type structures for the hauke.cloud IoT Alert Service API. You can import it as a dependency to access consistent data models for device alerts and notifications across your services. It is intended for developers in the hauke.cloud ecosystem who need standardized alert payloads without implementing business logic.

</llm>


## :book: Description

<llm description>

This repository provides a Go library that standardizes data structures for the hauke.cloud IoT Alert Service API. If you are building services that handle device alert thresholds and notifications, you can import this module to ensure all components use consistent type definitions instead of duplicating structs across your codebase. The package contains only data-transfer objects with no business logic or HTTP handlers, making it a lightweight dependency for internal service communication.

You consume the shared types by adding `github.com/hauke-cloud/iot-api/alerts` as a Go module dependency in your own projects. This keeps alert-related payloads aligned across the hauke.cloud ecosystem and reduces integration friction when services exchange threshold data or paginated device lists.

- Defines `AlertDevice` for devices triggering thresholds
- Exports `AlertConditionInfo` with measurement, operator, and threshold metadata
- Provides `AlertsResponse` as a paginated envelope containing device lists and counts
- Supplies `AlertFilters` for querying by device name, sensor type, location, room, or time window
- Includes `ErrorResponse` for standardized error payloads

</llm>


## :clipboard: Requirements

<llm requirements hint="Give the Terraform version from .terraform-version and the provider constraints from versions.tf, plus the credentials the providers need.">

- A Go toolchain matching version 1.26.2 (pinned in `go.mod`)
- The `pre-commit` Python package for local development workflows
- No cloud credentials or infrastructure access are required, as this repository contains only shared Go type definitions

</llm>


## 🚀 Getting started

<llm getting_started hint="terraform init, plan and apply, with the backend configuration the repository actually uses. Say plainly if apply touches real infrastructure.">

This repository provides shared Go type definitions for the IoT Alert Service API.

1. You start by cloning the repository and entering its directory.
```bash
git clone https://github.com/hauke-cloud/iot-api.git
cd iot-api
```
2. You install the pre-commit hooks to enforce code quality standards during development.
```bash
pre-commit install
```
3. You verify that the Go source compiles without errors using the conventional build command for this ecosystem.
```bash
go build ./...
```
4. You run the pre-commit checks across all files to confirm they pass your configured rules.
```bash
pre-commit run --all-files
```

</llm>


## :airplane: Usage

<llm usage hint="For a reusable module, the central example is a module block with source, version and the required variables filled in from variables.tf. For a root module, show the workflow instead.">

- **Consume as a dependency:** Add the module path to your project or fetch it directly:
  ```bash
  go get github.com/hauke-cloud/iot-api/alerts
  ```
  Once imported, you can reference the exported types such as `AlertDevice`, `AlertConditionInfo`, `AlertsResponse`, `AlertFilters`, and `ErrorResponse` in your own code. The package relies only on the standard library `time` package.

- **Install development hooks:** Set up the pre-commit workflow defined in `.pre-commit-config.yaml`:
  ```bash
  pre-commit install
  ```

- **Run checks and update revisions:** Verify your changes against all configured checks before committing:
  ```bash
  pre-commit run --all-files
  ```
  To keep hook versions current, run:
  ```bash
  pre-commit autoupdate
  ```

The repository requires a Go toolchain matching version 1.26.2 or compatible to build and consume the code. No credentials or infrastructure access are needed for standard usage.

</llm>


## :wrench: Configuration

<llm configuration hint="A table of the variables in variables.tf: name, type, default, required. Point at variables.tf for the full set and mention outputs.tf if it exists.">

This repository does not expose a Terraform configuration surface. Despite its classification and the presence of `.terraform-version` and `.opentofu-version` files from its template origin, there are no `.tf` source files, `variables.tf`, or provider configurations in the codebase. The package is strictly a Go library for shared type definitions, so infrastructure inputs, outputs, and state management are not applicable here. If you expect Terraform variables to configure deployments, they reside in the consuming services' repositories rather than this package. The version guard files currently pin Terraform to `1.9` and OpenTofu to `1.8.0`, but these have no effect without corresponding configuration files. For any future infrastructure code added to this repository, you would document it in `variables.tf` and reference `outputs.tf` if applicable.

</llm>


## :hammer: Development

<llm development hint="Cover terraform fmt, validate, tflint and terraform-docs where the repository configures them.">

To contribute to this repository, ensure you have Go 1.26.2 installed. The codebase contains no test files, so `go test ./...` will run without assertions, but you can verify compilation with `go build ./...`.

Code formatting and style are enforced through `.editorconfig` and pre-commit hooks. Install the hooks locally with:
```bash
pre-commit install
```
You can manually trigger all checks across the repository using:
```bash
pre-commit run --all-files
```
Update hook versions as needed with `pre-commit autoupdate`.

The continuous integration pipeline enforces two requirements for pull requests. First, it validates that your commit title follows conventional commit formatting. Second, it runs the configured pre-commit hooks on every push. Ensure all checks pass before requesting a review. This repository does not generate any files that require regeneration, and Terraform-related version files are template artifacts that do not apply to this Go library.

</llm>


## 📄 License

This Project is licensed under the GNU General Public License v3.0

- see the [LICENSE](LICENSE) file for details.


## :coffee: Contributing

To become a contributor, please check out the [CONTRIBUTING](CONTRIBUTING.md) file.


## :email: Contact

For any inquiries or support requests, please open an issue in this
repository or contact us at [contact@hauke.cloud](mailto:contact@hauke.cloud).
