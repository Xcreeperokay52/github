# Copyright 2019 Istio Authors. All Rights Reserved.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#    http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#
################################################################################
#

licenses(["notice"])

cc_library(
    name = "context",
    srcs = [
        "context.cc",
    ],
    hdrs = [
        "context.h",
    ],
    visibility = [
        "//extensions/stackdriver:__pkg__",
        "//extensions/stackdriver/metric:__pkg__",
    ],
    deps = [
        ":constants",
        ":node_info_cc_proto",
        "@com_google_protobuf//:protobuf",
    ],
)

cc_library(
    name = "constants",
    hdrs = [
        "constants.h",
    ],
)

cc_proto_library(
    name = "node_info_cc_proto",
    visibility = [
        "//extensions/stackdriver:__pkg__",
    ],
    deps = ["node_info_proto"],
)

proto_library(
    name = "node_info_proto",
    srcs = ["node_info.proto"],
)

cc_test(
    name = "context_test",
    size = "small",
    srcs = ["context_test.cc"],
    linkstatic = 1,
    deps = [
        ":context",
        "//external:googletest_main",
    ],
)