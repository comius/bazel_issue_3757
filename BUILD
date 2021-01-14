load("@bazel_tools//tools/jdk:default_java_toolchain.bzl", "default_java_toolchain")

default_java_toolchain(
  name = "myjava",
  xlint = [
    "all",
    "-processing",
    "-serial",
  ],
  misc = [
    "-Werror",
  ],
)

load("@grpc_java//:java_grpc_library.bzl", "java_grpc_library")


proto_library(
    name = "proto-library",
    srcs = ["helloworld.proto"],
)

java_proto_library(
    name = "messages-protobuf",
    deps = [":proto-library"],
)

java_grpc_library(
  name = "grpc-protobuf",
  srcs = [":proto-library"],
  deps = [":messages-protobuf"],
)
