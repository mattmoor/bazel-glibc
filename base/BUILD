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

docker_build(
    name = "java8",
    base = ":cc",
    entrypoint = [
       "./usr/lib/jvm/java-8-openjdk-amd64/jre/bin/java",
       "-jar",
       # We expect users to use:
       # cmd = ["/path/to/deploy.jar", "--option1", ...]
    ],
    debs = [
       "@zlib//file",
       "@openjdk_jre8//file",
    ],
)
