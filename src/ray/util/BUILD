load("//bazel:ray.bzl", "ray_cc_library")

ray_cc_library(
    name = "visibility",
    hdrs = ["visibility.h"],
)

ray_cc_library(
    name = "macros",
    hdrs = ["macros.h"],
)

ray_cc_library(
    name = "event_label",
    hdrs = ["event_label.h"],
)

ray_cc_library(
    name = "array",
    hdrs = ["array.h"],
)

ray_cc_library(
    name = "thread_utils",
    hdrs = ["thread_utils.h"],
    deps = [
        ":thread_checker",
    ],
)

ray_cc_library(
    name = "exponential_backoff",
    hdrs = ["exponential_backoff.h"],
    srcs = ["exponential_backoff.cc"],
    deps = [
        ":logging",
    ],
)

ray_cc_library(
    name = "logging",
    hdrs = ["logging.h"],
    srcs = ["logging.cc"],
    deps = [
        ":event_label",
        ":macros",
        ":string_utils",
        ":thread_utils",
        "@com_github_spdlog//:spdlog",
        "@com_google_absl//absl/debugging:failure_signal_handler",
        "@com_google_absl//absl/strings:str_format",
        "@com_google_googletest//:gtest_prod",
        "@nlohmann_json",
    ],
)

ray_cc_library(
    name = "filesystem",
    hdrs = ["filesystem.h"],
    srcs = ["filesystem.cc"],
    deps = [
        "//src/ray/common:status_or",
    ],
)

ray_cc_library(
    name = "container_util",
    hdrs = ["container_util.h"],
    deps = [
        ":logging",
        "@com_google_absl//absl/container:flat_hash_map",
        "@com_google_absl//absl/container:flat_hash_set",
        "@com_google_absl//absl/container:inlined_vector",
    ],
)

ray_cc_library(
    name = "process",
    hdrs = [
        "process.h",
        "subreaper.h",
    ],
    srcs = [
        "process.cc",
        "subreaper.cc",
    ],
    deps = [
        ":cmd_line_utils",
        ":filesystem",
        ":logging",
        ":macros",
        "@boost//:asio",
        "@com_google_absl//absl/container:flat_hash_set",
        "@com_google_absl//absl/synchronization",
    ],
)

ray_cc_library(
    name = "function_traits",
    hdrs = ["function_traits.h"],
    deps = [
        "@boost//:functional",
    ],
)

ray_cc_library(
    name = "counter_map",
    hdrs = ["counter_map.h"],
    deps = [
        ":logging",
    ],
)

ray_cc_library(
    name = "event",
    hdrs = ["event.h"],
    srcs = ["event.cc"],
    deps = [
        ":logging",
        ":random",
        ":string_utils",
        ":timestamp_utils",
        "//src/ray/protobuf:event_cc_proto",
        "//src/ray/protobuf:export_event_cc_proto",
        "@boost//:asio",
        "@com_github_spdlog//:spdlog",
        "@com_google_absl//absl/container:flat_hash_map",
        "@com_google_googletest//:gtest_prod",
        "@com_google_protobuf//:protobuf",
        "@nlohmann_json",
    ],
)

ray_cc_library(
    name = "timestamp_utils",
    hdrs = ["timestamp_utils.h"],
)

ray_cc_library(
    name = "random",
    hdrs = ["random.h"],
    deps = [
        "@com_google_absl//absl/random",
    ],
)

ray_cc_library(
    name = "string_utils",
    hdrs = ["string_utils.h"],
    srcs = ["string_utils.cc"],
)

ray_cc_library(
    name = "memory",
    hdrs = ["memory.h"],
    srcs = ["memory.cc"],
)

ray_cc_library(
    name = "type_traits",
    hdrs = ["type_traits.h"],
)

ray_cc_library(
    name = "throttler",
    hdrs = ["throttler.h"],
    deps = [
        "@com_google_absl//absl/time",
    ],
)

ray_cc_library(
    name = "sequencer",
    hdrs = ["sequencer.h"],
    deps = [
        "@com_google_absl//absl/container:flat_hash_map",
        "@com_google_absl//absl/synchronization",
    ],
)

ray_cc_library(
    name = "sample",
    hdrs = ["sample.h"],
)

ray_cc_library(
    name = "cmd_line_utils",
    hdrs = ["cmd_line_utils.h"],
    srcs = ["cmd_line_utils.cc"],
    deps = [
        ":logging",
        ":string_utils",
    ],
)

# TODO(hjiang): Split URL related functions into a separate util target.
ray_cc_library(
    name = "util",
    hdrs = ["util.h"],
    srcs = ["util.cc"],
    deps = [
        ":filesystem",
        ":logging",
        ":macros",
        ":process",
        "//:sha256",
        "@boost//:asio",
        "@com_google_absl//absl/container:flat_hash_map",
    ],
)

ray_cc_library(
    name = "size_literals",
    hdrs = ["size_literals.h"],
)

ray_cc_library(
    name = "thread_checker",
    hdrs = ["thread_checker.h"],
    srcs = ["thread_checker.cc"],

)

ray_cc_library(
    name = "map_utils",
    hdrs = ["map_utils.h"],
)

ray_cc_library(
    name = "shared_lru",
    hdrs = ["shared_lru.h"],
    deps = [
        ":map_utils",
        ":util",
        "@com_google_absl//absl/container:flat_hash_map",
    ],
)

ray_cc_library(
    name = "compat",
    hdrs = ["compat.h"],
    srcs = ["compat.cc"],
    deps = [
        ":logging",
        "//src/ray/common:status",
    ],
)

ray_cc_library(
    name = "stream_redirection_options",
    hdrs = ["stream_redirection_options.h"],
)

ray_cc_library(
    name = "pipe_logger",
    hdrs = ["pipe_logger.h"],
    srcs = ["pipe_logger.cc"],
    deps = [
        ":compat",
        ":spdlog_fd_sink",
        ":stream_redirection_options",
        ":thread_utils",
        ":util",
        "@boost//:iostreams",
        "@com_github_spdlog//:spdlog",
        "@com_google_absl//absl/container:inlined_vector",
        "@com_google_absl//absl/strings",
    ],
)

ray_cc_library(
    name = "stream_redirection_utils",
    hdrs = ["stream_redirection_utils.h"],
    srcs = ["stream_redirection_utils.cc"],
    deps = [
        ":pipe_logger",
        ":stream_redirection_options",
        ":util",
    ],
)

ray_cc_library(
    name = "spdlog_fd_sink",
    hdrs = ["spdlog_fd_sink.h"],
    deps = [
        ":compat",
        ":util",
        "@com_github_spdlog//:spdlog",
    ],
)

ray_cc_library(
    name = "temporary_directory",
    hdrs = ["temporary_directory.h"],
    srcs = ["temporary_directory.cc"],
    deps = [
        ":util",
        "@com_google_absl//absl/strings:str_format",
    ],
)
