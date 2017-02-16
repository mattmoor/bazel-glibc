package(default_visibility = ["//visibility:public"])

load("@bazel_tools//tools/build_defs/docker:docker.bzl", "docker_build")

java_binary(
    name = "Hello",
    srcs = ["Hello.java"],
)

docker_build(
    name = "java",
    base = "//base:java8",
    files = [":Hello_deploy.jar"],
    cmd = ["/Hello_deploy.jar"]
)
