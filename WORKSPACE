workspace(name = "bazel_glibc")

git_repository(
    name = "io_bazel_rules_go",
    remote = "https://github.com/bazelbuild/rules_go.git",
    tag = "0.4.0",
)

load("@io_bazel_rules_go//go:def.bzl", "go_repositories")

go_repositories()

# TODO(mattmoor): From docker_repositories()
# # For packaging python
# git_repository(
#     name = "subpar",
#     remote = "https://github.com/google/subpar",
#     commit = "74529f1df2178f07d34c72b3d270355dab2a10fc",
# )

# Rust rules
git_repository(
    name = "io_bazel_rules_rust",
    remote = "https://github.com/bazelbuild/rules_rust.git",
    tag = "0.0.5",
)
load("@io_bazel_rules_rust//rust:rust.bzl", "rust_repositories")

rust_repositories()

# Scala rules
git_repository(
    name = "io_bazel_rules_scala",
    remote = "https://github.com/bazelbuild/rules_scala.git",
    commit = "73743b830ae98d13a946b25ad60cad5fee58e6d3", # update this as needed
)

load("@io_bazel_rules_scala//scala:scala.bzl", "scala_repositories")
scala_repositories()

# D rules
git_repository(
    name = "io_bazel_rules_d",
    remote = "https://github.com/bazelbuild/rules_d.git",
    commit = "0019cde76f74f78e7ec58f14284ec72ed9283014",
)

load("@io_bazel_rules_d//d:d.bzl", "d_repositories")
d_repositories()

# For everything.
http_file(
   name = "glibc",
   url = "http://ftp.us.debian.org/debian/pool/main/g/glibc/libc6_2.19-18+deb8u7_amd64.deb",
)

# For C++
http_file(
   name = "libgcc1",
   url = "http://ftp.us.debian.org/debian/pool/main/g/gcc-4.9/libgcc1_4.9.2-10_amd64.deb",
)

http_file(
   name = "libstdcpp6",
   url = "http://ftp.us.debian.org/debian/pool/main/g/gcc-4.9/libstdc++6_4.9.2-10_amd64.deb",
)

# For Java and Python
http_file(
   name = "zlib",
   url = "http://ftp.us.debian.org/debian/pool/main/z/zlib/zlib1g_1.2.8.dfsg-2+b1_amd64.deb",
)

# For Java
http_file(
   name = "openjdk_jre8",
   url = "http://ftp.us.debian.org/debian/pool/main/o/openjdk-8/openjdk-8-jre-headless_8u121-b13-4.1_amd64.deb",
)

http_file(
   name = "libfreetype",
   url = "http://security.debian.org/debian-security/pool/updates/main/f/freetype/libfreetype6_2.5.2-3+deb8u2_amd64.deb",
)

http_file(
   name = "libpng",
   url = "http://ftp.us.debian.org/debian/pool/main/libp/libpng/libpng12-0_1.2.50-2+deb8u3_amd64.deb",
)

# For Python
http_file(
   name = "libpython27",
   url = "http://ftp.us.debian.org/debian/pool/main/p/python2.7/libpython2.7-minimal_2.7.9-2+deb8u1_amd64.deb",
)

http_file(
   name = "python27",
   url = "http://ftp.us.debian.org/debian/pool/main/p/python2.7/python2.7-minimal_2.7.9-2+deb8u1_amd64.deb",
)

# Docker rules.
git_repository(
    name = "io_bazel_rules_docker",
    remote = "https://github.com/bazelbuild/rules_docker.git",
    commit = "cd0363f77182689303f3d5a871348fa8ab78491e",
)

load(
  "@io_bazel_rules_docker//docker:docker.bzl",
  "docker_repositories",
)
docker_repositories()