load("@io_bazel_rules_go//go:def.bzl", "go_binary", "go_library")

go_library(
    name = "go_default_library",
    srcs = ["main.go"],
    importpath = "k8s.io/test-infra/prow/cmd/clonerefs",
    visibility = ["//visibility:private"],
    deps = [
        "//prow/kube:go_default_library",
        "//prow/pjutil:go_default_library",
        "//prow/pod-utils/clone:go_default_library",
        "//vendor/github.com/sirupsen/logrus:go_default_library",
    ],
)

go_binary(
    name = "clonerefs",
    embed = [":go_default_library"],
    importpath = "k8s.io/test-infra/prow/cmd/clonerefs",
    visibility = ["//visibility:public"],
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [":package-srcs"],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)
