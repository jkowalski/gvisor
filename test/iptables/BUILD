load("//tools:defs.bzl", "go_library", "go_test")

package(
    default_applicable_licenses = ["//:license"],
    licenses = ["notice"],
)

go_library(
    name = "iptables",
    testonly = 1,
    srcs = [
        "filter_input.go",
        "filter_output.go",
        "iptables.go",
        "iptables_unsafe.go",
        "iptables_util.go",
        "nat.go",
    ],
    visibility = ["//test/iptables:__subpackages__"],
    deps = [
        "//pkg/binary",
        "//pkg/hostarch",
        "//pkg/test/testutil",
        "@org_golang_x_sys//unix:go_default_library",
    ],
)

go_test(
    name = "iptables_test",
    size = "large",
    srcs = [
        "iptables_test.go",
    ],
    data = ["//test/iptables/runner"],
    library = ":iptables",
    tags = [
        "local",
        "manual",
    ],
    deps = [
        "//pkg/test/dockerutil",
        "//pkg/test/testutil",
    ],
)
