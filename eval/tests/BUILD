# This package contains CEL evaluator tests (end-to-end, benchmark etc.)
#
#

package(default_visibility = ["//visibility:public"])

licenses(["notice"])  # Apache 2.0

exports_files(["LICENSE"])

cc_test(
    name = "benchmark_test",
    size = "small",
    srcs = [
        "benchmark_test.cc",
    ],
    tags = ["manual"],
    deps = [
        ":request_context_cc_proto",
        "//eval/public:activation",
        "//eval/public:builtin_func_registrar",
        "//eval/public:cel_expr_builder_factory",
        "//eval/public:cel_expression",
        "//eval/public:cel_value",
        "//eval/public/containers:container_backed_list_impl",
        "//eval/public/structs:cel_proto_wrapper",
        "@com_github_google_googlebench//:benchmark",
        "@com_github_google_googlebench//:benchmark_main",
        "@com_google_absl//absl/base:core_headers",
        "@com_google_absl//absl/container:node_hash_set",
        "@com_google_absl//absl/strings",
        "@com_google_googleapis//google/api/expr/v1alpha1:syntax_cc_proto",
        "@com_google_googletest//:gtest_main",
        "@com_google_protobuf//:protobuf",
    ],
)

cc_test(
    name = "end_to_end_test",
    size = "small",
    srcs = [
        "end_to_end_test.cc",
    ],
    deps = [
        "//base:status_macros",
        "//eval/public:activation",
        "//eval/public:builtin_func_registrar",
        "//eval/public:cel_expr_builder_factory",
        "//eval/public:cel_expression",
        "//eval/public:cel_value",
        "//eval/public/structs:cel_proto_wrapper",
        "//eval/testutil:test_message_cc_proto",
        "@com_google_googleapis//google/api/expr/v1alpha1:syntax_cc_proto",
        "@com_google_googletest//:gtest_main",
        "@com_google_protobuf//:protobuf",
    ],
)

cc_test(
    name = "unknowns_end_to_end_test",
    size = "small",
    srcs = [
        "unknowns_end_to_end_test.cc",
    ],
    deps = [
        "//base:status_macros",
        "//eval/eval:evaluator_core",
        "//eval/public:activation",
        "//eval/public:builtin_func_registrar",
        "//eval/public:cel_attribute",
        "//eval/public:cel_expr_builder_factory",
        "//eval/public:cel_expression",
        "//eval/public:cel_function",
        "//eval/public:cel_options",
        "//eval/public:cel_value",
        "//eval/public:unknown_set",
        "//eval/public/containers:container_backed_list_impl",
        "//eval/public/containers:container_backed_map_impl",
        "//eval/public/structs:cel_proto_wrapper",
        "@com_google_absl//absl/container:btree",
        "@com_google_absl//absl/strings",
        "@com_google_absl//absl/types:span",
        "@com_google_googletest//:gtest_main",
        "@com_google_protobuf//:protobuf",
    ],
)

proto_library(
    name = "request_context_protos",
    srcs = [
        "request_context.proto",
    ],
)

cc_proto_library(
    name = "request_context_cc_proto",
    deps = [":request_context_protos"],
)

cc_library(
    name = "mock_cel_expression",
    testonly = 1,
    hdrs = ["mock_cel_expression.h"],
    deps = [
        "//eval/public:activation",
        "//eval/public:cel_expression",
        "@com_google_googletest//:gtest",
    ],
)
