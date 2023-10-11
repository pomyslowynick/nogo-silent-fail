workspace(name = "nogo-test")

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")
load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")

# start rules_go / bazel_gazelle
bazel_rules_go_version = "v0.41.0"


http_archive(
    name = "io_bazel_rules_go",
    sha256 = "278b7ff5a826f3dc10f04feaf0b70d48b68748ccd512d7f98bf442077f043fe3",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/rules_go/releases/download/%s/rules_go-%s.zip" % (bazel_rules_go_version, bazel_rules_go_version),
        "https://github.com/bazelbuild/rules_go/releases/download/%s/rules_go-%s.zip" % (bazel_rules_go_version, bazel_rules_go_version),
    ],
)

bazel_gazelle_version = "v0.33.0"

http_archive (
    name = "bazel_gazelle",
    sha256 = "d3fa66a39028e97d76f9e2db8f1b0c11c099e8e01bf363a923074784e451f809",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/bazel-gazelle/releases/download/%s/bazel-gazelle-%s.tar.gz" % (bazel_gazelle_version, bazel_gazelle_version),
        "https://github.com/bazelbuild/bazel-gazelle/releases/download/%s/bazel-gazelle-%s.tar.gz" % (bazel_gazelle_version, bazel_gazelle_version),
    ],
)

load("@io_bazel_rules_go//go:deps.bzl", "go_register_toolchains", "go_rules_dependencies")

go_rules_dependencies()

rules_jsonnet_version = "0.5.0"

http_archive(
    name = "io_bazel_rules_jsonnet",
    sha256 = "c51ba0dba41d667fa5c64e56e252ba54be093e5ae764af6470dabca901f373eb",
    strip_prefix = "rules_jsonnet-%s" % rules_jsonnet_version,
    urls = ["https://github.com/bazelbuild/rules_jsonnet/archive/%s.tar.gz" % rules_jsonnet_version],
)



go_register_toolchains(nogo = "@//:nogo-linter", version = "1.21.1")
