
pre-commit-golang
=================

golang hooks for http://pre-commit.com/

### install pre-commit

```shell
brew install pre-commit
```

### 进入你自己的仓库目录,执行以下命令, 生成.git/hooks/pre-commit

```shell
pre-commit install
```

### Using these hooks

Add this to your `.pre-commit-config.yaml`

    - repo: git://github.com/zhuqiuzhi/pre-commit-golang
      sha: HEAD
      hooks:
        - id: go-fmt
        - id: go-vet
        - id: go-build

### Available hooks

- `go-fmt` - Runs `gofmt`, requires golang
- `go-vet` - Runs `go vet`, requires golang
- `go-lint` - Runs `golint`, requires https://github.com/golang/lint
- `validate-toml` - Runs `tomlv`, requires
   https://github.com/BurntSushi/toml/tree/master/cmd/tomlv
- `no-go-testing` - Checks that no files are using `testing.T`, if you want
  developers to use a different testing framework
- `gometalinter` - run `gometalinter --config gometalinter.json ./...`
- `golangci-lint` - run `golangci-lint run ./...`, requires
  [golangci-lint](https://github.com/golangci/golangci-lint)
- `go-critic` - run `gocritic check-project .`, requires [go-critic](https://github.com/go-critic/go-critic)
- `go-unit-tests` - run `go test -tags=unit -timeout 30s -short -v`
- `go-build` - run `go build`, requires golang
