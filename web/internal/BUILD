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

load("@io_bazel_skydoc//skylark:skylark.bzl", "skylark_doc", "skylark_library")

skylark_library(
    name = "web_test_rules",
    srcs = glob(["*.bzl"]),
)

skylark_doc(
    name = "web_test_docs",
    format = "markdown",
    tags = ["manual"],
    deps = [":web_test_rules"],
)

exports_files(glob(["*.bzl"]))