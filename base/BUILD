package(default_visibility = ["//visibility:public"])

load("@bazel_tools//tools/build_defs/docker:docker.bzl", "docker_build")

docker_build(
    name = "base",
    debs = ["@glibc//file"],
)

docker_build(
    name = "cc",
    base = ":base",
    debs = [
       "@libgcc1//file",
       "@libstdcpp6//file",
    ],
)
