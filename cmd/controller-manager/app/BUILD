load("@io_bazel_rules_go//go:def.bzl", "go_library", "go_test")

go_library(
    name = "go_default_library",
    srcs = [
        "helper.go",
        "serve.go",
    ],
    importpath = "k8s.io/kubernetes/cmd/controller-manager/app",
    visibility = ["//visibility:public"],
    deps = [
        "//staging/src/k8s.io/apimachinery/pkg/util/sets:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/util/wait:go_default_library",
        "//staging/src/k8s.io/apiserver/pkg/endpoints/filters:go_default_library",
        "//staging/src/k8s.io/apiserver/pkg/endpoints/request:go_default_library",
        "//staging/src/k8s.io/apiserver/pkg/server:go_default_library",
        "//staging/src/k8s.io/apiserver/pkg/server/filters:go_default_library",
        "//staging/src/k8s.io/apiserver/pkg/server/healthz:go_default_library",
        "//staging/src/k8s.io/apiserver/pkg/server/mux:go_default_library",
        "//staging/src/k8s.io/apiserver/pkg/server/routes:go_default_library",
        "//staging/src/k8s.io/client-go/kubernetes:go_default_library",
        "//staging/src/k8s.io/client-go/kubernetes/scheme:go_default_library",
        "//staging/src/k8s.io/component-base/config:go_default_library",
        "//staging/src/k8s.io/component-base/configz:go_default_library",
        "//staging/src/k8s.io/component-base/metrics/legacyregistry:go_default_library",
        "//staging/src/k8s.io/component-base/metrics/prometheus/workqueue:go_default_library",
        "//vendor/k8s.io/klog:go_default_library",
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
    srcs = [
        ":package-srcs",
        "//cmd/controller-manager/app/options:all-srcs",
    ],
    tags = ["automanaged"],
    visibility = ["//visibility:public"],
)

go_test(
    name = "go_default_test",
    srcs = ["helper_test.go"],
    embed = [":go_default_library"],
    deps = [
        "//staging/src/k8s.io/apimachinery/pkg/util/sets:go_default_library",
        "//vendor/github.com/stretchr/testify/assert:go_default_library",
    ],
)
