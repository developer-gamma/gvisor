package(licenses = ["notice"])  # Apache 2.0

load("@io_bazel_rules_go//go:def.bzl", "go_library")
load("//tools/go_stateify:defs.bzl", "go_stateify")

go_stateify(
    name = "hostinet_state",
    srcs = [
        "save_restore.go",
        "socket.go",
        "stack.go",
    ],
    out = "hostinet_autogen_state.go",
    package = "hostinet",
)

go_library(
    name = "hostinet",
    srcs = [
        "device.go",
        "hostinet.go",
        "hostinet_autogen_state.go",
        "save_restore.go",
        "socket.go",
        "socket_unsafe.go",
        "stack.go",
    ],
    importpath = "gvisor.googlesource.com/gvisor/pkg/sentry/socket/hostinet",
    visibility = ["//pkg/sentry:internal"],
    deps = [
        "//pkg/abi/linux",
        "//pkg/binary",
        "//pkg/log",
        "//pkg/sentry/arch",
        "//pkg/sentry/context",
        "//pkg/sentry/device",
        "//pkg/sentry/fs",
        "//pkg/sentry/fs/fsutil",
        "//pkg/sentry/inet",
        "//pkg/sentry/kernel",
        "//pkg/sentry/kernel/kdefs",
        "//pkg/sentry/kernel/time",
        "//pkg/sentry/safemem",
        "//pkg/sentry/socket",
        "//pkg/sentry/usermem",
        "//pkg/state",
        "//pkg/syserr",
        "//pkg/syserror",
        "//pkg/tcpip/transport/unix",
        "//pkg/waiter",
        "//pkg/waiter/fdnotifier",
    ],
)
