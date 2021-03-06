licenses(["notice"])  # Apache 2

load(
    "//bazel:envoy_build_system.bzl",
    "envoy_cc_test",
    "envoy_package",
)

envoy_package()

envoy_cc_test(
    name = "config_test",
    srcs = ["config_test.cc"],
    deps = [
        "//source/common/config:well_known_names",
        "//source/common/protobuf",
        "//source/common/protobuf:utility_lib",
        "//source/common/router:router_lib",
        "//source/server/config/http:buffer_lib",
        "//source/server/config/http:dynamo_lib",
        "//source/server/config/http:ext_authz_lib",
        "//source/server/config/http:fault_lib",
        "//source/server/config/http:grpc_http1_bridge_lib",
        "//source/server/config/http:grpc_json_transcoder_lib",
        "//source/server/config/http:grpc_web_lib",
        "//source/server/config/http:ip_tagging_lib",
        "//source/server/config/http:lua_lib",
        "//source/server/config/http:ratelimit_lib",
        "//source/server/config/http:router_lib",
        "//source/server/config/http:squash_lib",
        "//source/server/config/http:zipkin_lib",
        "//source/server/http:health_check_lib",
        "//test/mocks/access_log:access_log_mocks",
        "//test/mocks/server:server_mocks",
        "//test/test_common:utility_lib",
    ],
)

envoy_cc_test(
    name = "lightstep_config_test",
    srcs = ["lightstep_config_test.cc"],
    deps = [
        "//source/server/config/http:lightstep_lib",
        "//test/mocks/server:server_mocks",
        "//test/test_common:utility_lib",
    ],
)

envoy_cc_test(
    name = "dynamic_opentracing_config_test",
    srcs = ["dynamic_opentracing_config_test.cc"],
    data = [
        "@io_opentracing_cpp//mocktracer:libmocktracer_plugin.so",
    ],
    deps = [
        "//source/server/config/http:dynamic_opentracing_lib",
        "//test/mocks/server:server_mocks",
        "//test/test_common:environment_lib",
        "//test/test_common:utility_lib",
    ],
)
