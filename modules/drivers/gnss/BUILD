load("//tools:cpplint.bzl", "cpplint")

package(default_visibility = ["//visibility:public"])

cc_binary(
    name = "libgnss_component.so",
    deps = [":gnss_component_lib"],
    linkopts = ["-shared"],
    linkstatic = False,
)

cc_library(
    name = "gnss_component_lib",
    srcs = ["gnss_component.cc"],
    hdrs = ["gnss_component.h"],
    deps = [
        "//cyber",
        "//modules/common/monitor_log",
        "//modules/drivers/gnss/stream:gnss_stream",
    ],
    copts = ['-DMODULE_NAME=\\"gnss\\"']
)

cpplint()
