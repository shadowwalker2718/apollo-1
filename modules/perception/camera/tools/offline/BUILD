load("//tools:cpplint.bzl", "cpplint")

package(default_visibility = ["//visibility:public"])


cc_library(
    name = "visualizer",
    srcs = [
        "visualizer.cc",
    ],
    linkopts = [
        "-lopencv_core",
        "-lopencv_imgproc",
        "-lopencv_highgui",
    ],
    hdrs = [
        "visualizer.h",
    ],
    deps = [
        ":transform_server",
        "//modules/perception/camera/common:common",
    ]
)

cc_library(
    name = "transform_server",
    srcs = [
        "transform_server.cc",
    ],
    hdrs = [
        "transform_server.h",
    ],
    deps = [
        "//cyber",
        "//modules/perception/base:base",
        "//modules/perception/camera/common:common",
        "@eigen",
        "@yaml_cpp//:yaml",
    ]
)

cc_binary(
    name = "offline_obstacle_pipeline",
    srcs = [
        "offline_obstacle_pipeline.cc",
    ],
    linkopts = [
        "-lopencv_core",
        "-lopencv_imgproc",
        "-lopencv_highgui",
        "-lboost_system",
    ],
    deps = [
        ":transform_server",
        ":visualizer",
        "//modules/perception/base:base",
        "//modules/perception/camera/app:obstacle_camera_perception",
        "//modules/perception/camera/common:common",
        "//modules/perception/lib/utils:utils",
    ]
)

cpplint()
