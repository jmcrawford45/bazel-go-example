load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "io_bazel_rules_go",
    sha256 = "2b1641428dff9018f9e85c0384f03ec6c10660d935b750e3fa1492a281a53b0f",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/rules_go/releases/download/v0.29.0/rules_go-v0.29.0.zip",
        "https://github.com/bazelbuild/rules_go/releases/download/v0.29.0/rules_go-v0.29.0.zip",
    ],
)

http_archive(
    name = "bazel_gazelle",
    sha256 = "de69a09dc70417580aabf20a28619bb3ef60d038470c7cf8442fafcf627c21cb",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/bazel-gazelle/releases/download/v0.24.0/bazel-gazelle-v0.24.0.tar.gz",
        "https://github.com/bazelbuild/bazel-gazelle/releases/download/v0.24.0/bazel-gazelle-v0.24.0.tar.gz",
    ],
)

load("@io_bazel_rules_go//go:deps.bzl", "go_register_toolchains", "go_rules_dependencies")
load("@bazel_gazelle//:deps.bzl", "gazelle_dependencies", "go_repository")

############################################################
# Define your own dependencies here using go_repository.
# Else, dependencies declared by rules_go/gazelle will be used.
# The first declaration of an external repository "wins".
############################################################
go_repository(
                name = "com_github_twitter_scoot",
                importpath = "github.com/twitter/scoot",
                strip_prefix = "one_level",
                urls = ["93bb2e82eb6421f8eb1abb5f7f76a5c41f21592d.tar.gz"],
            )

go_repository(
        name = "com_github_sirupsen_logrus",
        importpath = "github.com/sirupsen/logrus",
        strip_prefix = "one_level",
        urls = ["v1.4.2.tar.gz"],
    )

go_repository(
        name = "com_github_apache_thrift",
        importpath = "github.com/apache/thrift",
        strip_prefix = "one_level",
        urls = ["v0.0.0-20160616201512-0e9fed1e12ed.tar.gz"],
    )

go_rules_dependencies()

go_register_toolchains(version = "1.17.2")

gazelle_dependencies()