load("//tools:cpplint.bzl", "cpplint")

package(default_visibility = ["//visibility:public"])

cc_binary(
    name = "libvelodyne_convert_component.so",
    deps = [":velodyne_convert_component_lib"],
    linkopts = ["-shared"],
    linkstatic = False,
)

cc_library(
    name = "velodyne_convert_component_lib",
    srcs = ["velodyne_convert_component.cc"],
    hdrs = ["velodyne_convert_component.h"],
    deps = [
        "//cyber",
        "//modules/drivers/velodyne/parser:convert",
    ],
    copts = ['-DMODULE_NAME=\\"velodyne\\"']
)

cc_library(
    name = "convert",
    srcs = [
        "calibration.cc",
        "convert.cc",
        "online_calibration.cc",
        "velodyne128_parser.cc",
        "velodyne64_parser.cc",
        "velodyne32_parser.cc",
        "velodyne16_parser.cc",
        "velodyne_parser.cc",
        "util.cc",
    ],
    hdrs = [
        "calibration.h",
        "convert.h",
        "online_calibration.h",
        "const_variables.h",
        "util.h",
        "velodyne_parser.h",
    ],
    deps = [
        "//cyber",
        "//modules/drivers/proto:sensor_proto",
        "//modules/drivers/velodyne/proto:velodyne_proto",
        "@eigen",
        "@yaml_cpp//:yaml",
    ],
    copts = ['-DMODULE_NAME=\\"velodyne\\"']
)

cpplint()
