workspace(name = "bazel_glibc")

git_repository(
    name = "io_bazel_rules_go",
    remote = "https://github.com/bazelbuild/rules_go.git",
    tag = "0.4.0",
)

load("@io_bazel_rules_go//go:def.bzl", "go_repositories")

go_repositories()

git_repository(
    name = "subpar",
    remote = "https://github.com/google/subpar",
    commit = "74529f1df2178f07d34c72b3d270355dab2a10fc",
)


# You can browse the parent directory in a browser.
http_file(
   name = "glibc",
   url = "http://ftp.us.debian.org/debian/pool/main/g/glibc/libc6_2.19-18+deb8u7_amd64.deb",
)

http_file(
   name = "libgcc1",
   url = "http://ftp.us.debian.org/debian/pool/main/g/gcc-4.9/libgcc1_4.9.2-10_amd64.deb",
)

http_file(
   name = "libstdcpp6",
   url = "http://ftp.us.debian.org/debian/pool/main/g/gcc-4.9/libstdc++6_4.9.2-10_amd64.deb",
)
