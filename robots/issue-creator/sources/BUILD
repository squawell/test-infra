load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "flakyjob-reporter.go",
        "triage-filer.go",
    ],
    importpath = "k8s.io/test-infra/robots/issue-creator/sources",
    visibility = ["//visibility:public"],
    deps = [
        "//mungegithub/mungers/mungerutil:go_default_library",
        "//robots/issue-creator/creator:go_default_library",
        "//vendor/github.com/golang/glog:go_default_library",
        "//vendor/github.com/google/go-github/github:go_default_library",
    ],
)

go_test(
    name = "go_default_test",
    srcs = [
        "flakyjob-reporter_test.go",
        "triage-filer_test.go",
    ],
    embed = [":go_default_library"],
    importpath = "k8s.io/test-infra/robots/issue-creator/sources",
    deps = [
        "//robots/issue-creator/creator:go_default_library",
        "//robots/issue-creator/testowner:go_default_library",
        "//vendor/github.com/google/go-github/github:go_default_library",
    ],
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
