load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

protobuf_repository="protocolbuffers"
protobuf_version="3.6.x"
protobuf_sha256="d7eb198978163939b7e88c021441bcd58dd4f5cef47a83d2d22bee4316a11b57"
http_archive(
    name = "com_google_protobuf",
    sha256 = protobuf_sha256,
    strip_prefix = "protobuf-%s" % (protobuf_version),
    urls = ["https://github.com/%s/protobuf/archive/%s.zip" % (protobuf_repository, protobuf_version)],
)

rules_scala_version="8092d5f6165a8d9c4797d5f089c1ba4eee3326b1" # update this as needed
rules_scala_repository="bazelbuild"
rules_scala_sha256="db536b9db36b5aa737db9d08fa05d1fa5531c9cf213b04bed4e9b9fc34cc2390"
http_archive(
             name = "io_bazel_rules_scala",
             sha256 = rules_scala_sha256,
             url = "https://github.com/%s/rules_scala/archive/%s.zip"%(rules_scala_repository, rules_scala_version),
             type = "zip",
             strip_prefix= "rules_scala-%s" % rules_scala_version
             )
load("@io_bazel_rules_scala//scala:scala.bzl", "scala_repositories")

rules_scala_external_version = "8e9fefb7931768cd2bb10c715a42ab8d3e163b03"
rules_scala_external_sha256 = "8c5e2369c3c33fb3370dd585ffc442d06644146be73907bb525c68e1643f685b"
http_archive(
    name = "rules_jvm_external",
    strip_prefix = "rules_jvm_external-%s" % rules_scala_external_version,
    sha256 = rules_scala_external_sha256,
    url = "https://github.com/%s/rules_jvm_external/archive/%s.zip" % (rules_scala_repository, rules_scala_external_version),
)

scala_repositories(("2.11.12", {
   "scala_compiler": "3e892546b72ab547cb77de4d840bcfd05c853e73390fed7370a8f19acb0735a0",
   "scala_library": "0b3d6fd42958ee98715ba2ec5fe221f4ca1e694d7c981b0ae0cd68e97baf6dce",
   "scala_reflect": "6ba385b450a6311a15c918cf8688b9af9327c6104f0ecbd35933cfcd3095fe04"
}))

load("@io_bazel_rules_scala//scala:toolchains.bzl", "scala_register_toolchains")
scala_register_toolchains()

bazel_skylib_version = "0.8.0"
http_archive(
    name = "bazel_skylib",
    type = "tar.gz",
    url = "https://github.com/bazelbuild/bazel-skylib/releases/download/{}/bazel-skylib.{}.tar.gz".format (bazel_skylib_version, bazel_skylib_version),
    sha256 = "2ef429f5d7ce7111263289644d233707dba35e39696377ebab8b0bc701f7818e",
)

scala_toolchains_repository="bazelbuild"
scala_toolchains_version="d665ccfa3e9c90fa789671bf4ef5f7c19c5715c4"
scala_toolchains_sha256="4b1468b254a572dbe134cc1fd7c6eab1618a72acd339749ea343bd8f55c3b7eb"
http_archive(
  name = "bazel_toolchains",
  sha256 = scala_toolchains_sha256,
  strip_prefix = "bazel-toolchains-%s" % (scala_toolchains_version),
  urls = [
    "https://mirror.bazel.build/github.com/%s/bazel-toolchains/archive/%s.tar.gz" % (scala_toolchains_repository, scala_toolchains_version),
    "https://github.com/%s/bazel-toolchains/archive/%s.tar.gz" % (scala_toolchains_repository, scala_toolchains_version),
  ],
)
