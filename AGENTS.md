# AGENTS.md

## Build & Test Commands
- **Build:** `go build` or `./build.sh` (includes version info)
- **Docker build:** `docker build -f dockerfiles/Dockerfile.dev-self-contained -t watchtower:local .`
- **Run all tests:** `go test ./... -v`
- **Run single package tests:** `go test -v ./pkg/container/...`
- **Run single test by name:** `go test -v ./pkg/container/... -ginkgo.focus="test name pattern"`
- **Lint:** `staticcheck ./...`

## Code Style
- **Go version:** 1.20 | **Module:** `github.com/containrrr/watchtower`
- **Formatting:** Use `gofmt`; tabs for indentation (see `.editorconfig`)
- **Imports:** Standard library first, blank line, then third-party/internal packages
- **Naming:** PascalCase for exported, camelCase for unexported; short package aliases (`t`, `log`)
- **Errors:** Return errors up the stack; use `log.Fatal` for unrecoverable, `log.Error`/`log.Warn` otherwise
- **Comments:** Doc comments start with function/type name; use `//` style

## Testing
- Framework: Ginkgo/Gomega (BDD-style with `Describe`, `When`, `It`, `BeforeEach`)
- Test files: `*_test.go`, suite files: `*_suite_test.go`
- Import Gomega with dot notation: `. "github.com/onsi/gomega"`

## Key Dependencies
`docker/docker`, `spf13/cobra`, `spf13/viper`, `sirupsen/logrus`, `containrrr/shoutrrr`
