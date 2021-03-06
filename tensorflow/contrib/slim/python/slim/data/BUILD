# Description:
#   Contains packages used for creating and loading datasets.

licenses(["notice"])  # Apache 2.0

exports_files(["LICENSE"])

package(default_visibility = ["//tensorflow:__subpackages__"])

py_library(
    name = "data",
    deps = [
        ":dataset",
        ":dataset_data_provider",
        ":parallel_reader",
        ":prefetch_queue",
        ":tfexample_decoder",
    ],
)

py_library(
    name = "data_decoder",
    srcs = ["data_decoder.py"],
    srcs_version = "PY2AND3",
)

py_library(
    name = "data_provider",
    srcs = ["data_provider.py"],
    srcs_version = "PY2AND3",
)

py_library(
    name = "dataset",
    srcs = ["dataset.py"],
    srcs_version = "PY2AND3",
)

py_library(
    name = "dataset_data_provider",
    srcs = ["dataset_data_provider.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":data_provider",
        ":parallel_reader",
    ],
)

py_test(
    name = "dataset_data_provider_test",
    srcs = ["dataset_data_provider_test.py"],
    srcs_version = "PY2AND3",
    tags = ["manual"],  # Disabled due to http://b/29190340
    deps = [
        ":test_utils",
        "//tensorflow:tensorflow_py",
        "//tensorflow/contrib/slim",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:platform_test",
    ],
)

py_library(
    name = "parallel_reader",
    srcs = ["parallel_reader.py"],
    srcs_version = "PY2AND3",
    deps = [
        "//tensorflow/python:framework",
        "//tensorflow/python:ops",
        "//tensorflow/python:platform",
        "//tensorflow/python:training",
    ],
)

py_test(
    name = "parallel_reader_test",
    size = "small",
    srcs = ["parallel_reader_test.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":test_utils",
        "//tensorflow:tensorflow_py",
        "//tensorflow/contrib/slim",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:platform_test",
    ],
)

py_library(
    name = "prefetch_queue",
    srcs = ["prefetch_queue.py"],
    srcs_version = "PY2AND3",
    deps = [
        "//tensorflow/python:framework",
        "//tensorflow/python:ops",
        "//tensorflow/python:training",
    ],
)

py_test(
    name = "prefetch_queue_test",
    size = "small",
    srcs = ["prefetch_queue_test.py"],
    srcs_version = "PY2AND3",
    deps = [
        "//tensorflow:tensorflow_py",
        "//tensorflow/contrib/slim",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:platform_test",
    ],
)

py_library(
    name = "test_utils",
    srcs = ["test_utils.py"],
    srcs_version = "PY2AND3",
    deps = [
        "//tensorflow:tensorflow_py",
    ],
)

py_library(
    name = "tfexample_decoder",
    srcs = ["tfexample_decoder.py"],
    srcs_version = "PY2AND3",
    deps = [
        ":data_decoder",
        "//tensorflow/python:ops",
    ],
)

py_test(
    name = "tfexample_decoder_test",
    srcs = ["tfexample_decoder_test.py"],
    srcs_version = "PY2AND3",
    deps = [
        "//tensorflow:tensorflow_py",
        "//tensorflow/contrib/slim",
        "//tensorflow/python:framework_test_lib",
        "//tensorflow/python:platform_test",
    ],
)

filegroup(
    name = "all_files",
    srcs = glob(
        ["**/*"],
        exclude = [
            "**/METADATA",
            "**/OWNERS",
        ],
    ),
    visibility = ["//tensorflow:__subpackages__"],
)
