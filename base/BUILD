package(default_visibility = ["//visibility:public"])

load("@io_bazel_rules_docker//docker:docker.bzl", "docker_build")

# Create /tmp, too many things assume it exists.
docker_build(
    name = "with_tmp",
    directory = "/tmp",
    files = [":empty"],
)

docker_build(
    name = "base",
    base = ":with_tmp",
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
    name = "python27",
    base = ":base",
    entrypoint = [
       "/usr/bin/python2.7",
    ],
    debs = [
       "@zlib//file",
       "@python27//file",
       "@libpython27//file",
    ],
)

docker_build(
    name = "java8",
    base = ":cc",
    entrypoint = [
       "/usr/lib/jvm/java-8-openjdk-amd64/jre/bin/java",
       "-jar",
       # We expect users to use:
       # cmd = ["/path/to/deploy.jar", "--option1", ...]
    ],
    debs = [
       "@zlib//file",
       "@libfreetype//file",
       "@libpng//file",
       "@openjdk_jre8//file",
    ],
)

docker_build(
    name = "jetty",
    base = ":java8",
    tars = ["@jetty//:tar"],
    cmd = ["/jetty/start.jar"],
    workdir = "/jetty/demo-base/",
)
