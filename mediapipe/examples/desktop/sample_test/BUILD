# Copyright 2019 The MediaPipe Authors.
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

licenses(["notice"])

package(default_visibility = ["//mediapipe/examples:__subpackages__"])

cc_binary(
    name = "hello_world",
    srcs = ["main.cc"],
    deps = [
        # ":hello_world_library",
        # ":hand_tracking_cpu",
        ":holistic_tracking_cpu",
    ],
    # linkopts = ['-static'],    
    linkshared = True,
)

cc_library(
    name = "hello_world_library",
    srcs = ["hello_world.cc"],
    hdrs = ["hello_world.h"],
    visibility = ["//visibility:public"],
    deps = [
        "//mediapipe/calculators/core:pass_through_calculator",
        "//mediapipe/framework:calculator_graph",
        "//mediapipe/framework/port:logging",
        "//mediapipe/framework/port:parse_text_proto",
        "//mediapipe/framework/port:status",
    ],
)

cc_library(
    name = "hand_tracking_cpu",
    deps = [
        "//mediapipe/examples/desktop/sample_test:demo_run_graph_main",
        "//mediapipe/graphs/hand_tracking:desktop_tflite_calculators",
    ],
    copts = ['-fPIC'],
)

cc_library(
    name = "holistic_tracking_cpu",
    deps = [
        "//mediapipe/examples/desktop/sample_test:demo_run_graph_main",
        "//mediapipe/graphs/holistic_tracking:holistic_tracking_cpu_graph_deps",
    ],
)

cc_library(
    name = "demo_run_graph_main",
    srcs = ["demo_run_graph_main.cc"],
    hdrs = ["hello_world.h"],
    deps = [
        "//mediapipe/framework:calculator_framework",
        "//mediapipe/framework/formats:image_frame",
        "//mediapipe/framework/formats:image_frame_opencv",
        "//mediapipe/framework/port:file_helpers",
        "//mediapipe/framework/port:opencv_highgui",
        "//mediapipe/framework/port:opencv_imgproc",
        "//mediapipe/framework/port:opencv_video",
        "//mediapipe/framework/port:parse_text_proto",
        "//mediapipe/framework/port:status",
        "@com_google_absl//absl/flags:flag",
        "@com_google_absl//absl/flags:parse",
    ],
)