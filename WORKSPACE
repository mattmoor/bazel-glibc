workspace(name = "bazel_glibc")

git_repository(
    name = "io_bazel_rules_go",
    remote = "https://github.com/bazelbuild/rules_go.git",
    tag = "0.4.0",
)

load("@io_bazel_rules_go//go:def.bzl", "go_repositories")

go_repositories()

# You can browse the parent directory in a browser.
http_file(
   name = "glibc",
   url = "http://ftp.us.debian.org/debian/pool/main/e/eglibc/libc6_2.13-38+deb7u10_amd64.deb",
)