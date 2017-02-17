package(default_visibility = ["//visibility:public"])

load("@bazel_tools//tools/build_defs/docker:docker.bzl", "docker_build")

java_binary(
    name = "HelloJava",
    srcs = ["HelloJava.java"],
)

docker_build(
    name = "java",
    base = "//base:java8",
    files = [":HelloJava_deploy.jar"],
    cmd = ["/HelloJava_deploy.jar"]
)

load("@io_bazel_rules_scala//scala:scala.bzl", "scala_binary")

scala_binary(
    name = "HelloScala",
    srcs = ["HelloScala.scala"],
    main_class = "examples.HelloScala",
)

docker_build(
    name = "scala",
    base = "//base:java8",
    files = [":HelloScala_deploy.jar"],
    cmd = ["/HelloScala_deploy.jar"]
)
