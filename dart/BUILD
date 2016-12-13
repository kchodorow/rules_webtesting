# Copyright 2016 Google Inc.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#      http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#
################################################################################
#
package(default_testonly = True)

load("@io_bazel_rules_dart//dart/build_rules:core.bzl", "dart_library")
load("@io_bazel_rules_dart//dart/build_rules:vm.bzl", "dart_vm_test")
load("//web:web.bzl", "web_test_suite")

dart_library(
    name = "dart",
    srcs = glob(["lib/**/*.dart"]),
    pub_pkg_name = "webtest",
    visibility = ["//visibility:public"],
    deps = ["@com_github_google_webdriver_dart//:webdriver"],
)

dart_vm_test(
    name = "webtest_test_wrapped",
    srcs = glob(["test/**/*.dart"]),
    script_file = "test/webtest_test.dart",
    tags = [
        "manual",
        "noci",
    ],
    deps = [
        ":dart",
        "@org_dartlang_pub_test//:test",
    ],
)

web_test_suite(
    name = "webtest_test",
    browsers = ["//browsers:chromium-native"],
    local = True,
    tags = ["noci"],
    test = ":webtest_test_wrapped",
)