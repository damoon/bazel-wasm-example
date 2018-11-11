load("@bazel_gazelle//:def.bzl", "gazelle")

# gazelle:prefix github.com/damoon/bazel-wasm-example
gazelle(name = "gazelle")


load("@k8s_deploy//:defaults.bzl", "k8s_deploy")
k8s_deploy(
  name = "dev",
  template = ":deployment.yaml",
  images = {
    "registry.31j.de/lab/testing": "//cmd/server:image"
  },
)
