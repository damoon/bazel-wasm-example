running
```
bazel build //cmd/wasm --sandbox_debug --verbose_failures
```
fails with
```
INFO: Analysed target //cmd/wasm:wasm (0 packages loaded, 0 targets configured).
INFO: Found 1 target...
ERROR: /home/david/.cache/bazel/_bazel_david/d028113dbc50ecb39802891af462884e/external/io_bazel_rules_go/BUILD.bazel:9:1: GoStdlib external/io_bazel_rules_go/js_wasm_stripped/stdlib%/pkg failed (Exit 1) linux-sandbox failed: error executing command 
  (cd /home/david/.cache/bazel/_bazel_david/d028113dbc50ecb39802891af462884e/execroot/__main__ && \
  exec env - \
    CC=/usr/bin/gcc \
    CGO_CFLAGS='-U_FORTIFY_SOURCE -fstack-protector -B/usr/bin -B/usr/bin -Wunused-but-set-parameter -Wno-free-nonheap-object -fno-omit-frame-pointer -fno-canonical-system-headers -Wno-builtin-macro-redefined -D__DATE__="redacted" -D__TIMESTAMP__="redacted" -D__TIME__="redacted"' \
    CGO_ENABLED=1 \
    CGO_LDFLAGS='-fuse-ld=gold -Wl,-no-as-needed -Wl,-z,relro,-z,now -B/usr/bin -B/usr/bin -pass-exit-codes -lstdc++ -lm' \
    GOARCH=wasm \
    GOOS=js \
    GOROOT=external/go_sdk \
    GOROOT_FINAL=GOROOT \
    PATH=/usr/bin:/bin \
    TMPDIR=/tmp \
  /home/david/.cache/bazel/_bazel_david/d028113dbc50ecb39802891af462884e/execroot/__main__/_bin/linux-sandbox -t 15 -w /home/david/.cache/bazel/_bazel_david/d028113dbc50ecb39802891af462884e/sandbox/linux-sandbox/1/execroot/__main__ -w /tmp -w /dev/shm -D -- bazel-out/host/bin/external/io_bazel_rules_go/go/tools/builders/linux_amd64_stripped/stdlib -sdk external/go_sdk -installsuffix js_wasm -out bazel-out/k8-fastbuild/bin/external/io_bazel_rules_go/js_wasm_stripped/stdlib% -filter_buildid bazel-out/host/bin/external/io_bazel_rules_go/go/tools/builders/linux_amd64_stripped/filter_buildid): linux-sandbox failed: error executing command 
  (cd /home/david/.cache/bazel/_bazel_david/d028113dbc50ecb39802891af462884e/execroot/__main__ && \
  exec env - \
    CC=/usr/bin/gcc \
    CGO_CFLAGS='-U_FORTIFY_SOURCE -fstack-protector -B/usr/bin -B/usr/bin -Wunused-but-set-parameter -Wno-free-nonheap-object -fno-omit-frame-pointer -fno-canonical-system-headers -Wno-builtin-macro-redefined -D__DATE__="redacted" -D__TIMESTAMP__="redacted" -D__TIME__="redacted"' \
    CGO_ENABLED=1 \
    CGO_LDFLAGS='-fuse-ld=gold -Wl,-no-as-needed -Wl,-z,relro,-z,now -B/usr/bin -B/usr/bin -pass-exit-codes -lstdc++ -lm' \
    GOARCH=wasm \
    GOOS=js \
    GOROOT=external/go_sdk \
    GOROOT_FINAL=GOROOT \
    PATH=/usr/bin:/bin \
    TMPDIR=/tmp \
  /home/david/.cache/bazel/_bazel_david/d028113dbc50ecb39802891af462884e/execroot/__main__/_bin/linux-sandbox -t 15 -w /home/david/.cache/bazel/_bazel_david/d028113dbc50ecb39802891af462884e/sandbox/linux-sandbox/1/execroot/__main__ -w /tmp -w /dev/shm -D -- bazel-out/host/bin/external/io_bazel_rules_go/go/tools/builders/linux_amd64_stripped/stdlib -sdk external/go_sdk -installsuffix js_wasm -out bazel-out/k8-fastbuild/bin/external/io_bazel_rules_go/js_wasm_stripped/stdlib% -filter_buildid bazel-out/host/bin/external/io_bazel_rules_go/go/tools/builders/linux_amd64_stripped/filter_buildid)
src/main/tools/linux-sandbox.cc:154: linux-sandbox-pid1 has PID 30190
src/main/tools/linux-sandbox-pid1.cc:175: working dir: /home/david/.cache/bazel/_bazel_david/d028113dbc50ecb39802891af462884e/sandbox/linux-sandbox/1/execroot/__main__
src/main/tools/linux-sandbox-pid1.cc:194: writable: /home/david/.cache/bazel/_bazel_david/d028113dbc50ecb39802891af462884e/sandbox/linux-sandbox/1/execroot/__main__
src/main/tools/linux-sandbox-pid1.cc:194: writable: /tmp
src/main/tools/linux-sandbox-pid1.cc:194: writable: /dev/shm
src/main/tools/linux-sandbox-pid1.cc:265: remount ro: /
src/main/tools/linux-sandbox-pid1.cc:265: remount ro: /dev
src/main/tools/linux-sandbox-pid1.cc:265: remount ro: /dev/pts
src/main/tools/linux-sandbox-pid1.cc:265: remount rw: /dev/shm
src/main/tools/linux-sandbox-pid1.cc:265: remount ro: /dev/hugepages
src/main/tools/linux-sandbox-pid1.cc:265: remount ro: /dev/mqueue
src/main/tools/linux-sandbox-pid1.cc:265: remount ro: /run
src/main/tools/linux-sandbox-pid1.cc:265: remount ro: /run/lock
src/main/tools/linux-sandbox-pid1.cc:265: remount ro: /run/user/1001
src/main/tools/linux-sandbox-pid1.cc:265: remount ro: /run/user/1001/gvfs
src/main/tools/linux-sandbox-pid1.cc:265: remount ro: /run/docker/netns/default
src/main/tools/linux-sandbox-pid1.cc:265: remount ro: /sys
src/main/tools/linux-sandbox-pid1.cc:265: remount ro: /sys/kernel/security
src/main/tools/linux-sandbox-pid1.cc:265: remount ro: /sys/fs/cgroup
src/main/tools/linux-sandbox-pid1.cc:265: remount ro: /sys/fs/cgroup/systemd
src/main/tools/linux-sandbox-pid1.cc:265: remount ro: /sys/fs/cgroup/net_cls,net_prio
src/main/tools/linux-sandbox-pid1.cc:265: remount ro: /sys/fs/cgroup/cpuset
src/main/tools/linux-sandbox-pid1.cc:265: remount ro: /sys/fs/cgroup/cpu,cpuacct
src/main/tools/linux-sandbox-pid1.cc:265: remount ro: /sys/fs/cgroup/perf_event
src/main/tools/linux-sandbox-pid1.cc:265: remount ro: /sys/fs/cgroup/pids
src/main/tools/linux-sandbox-pid1.cc:265: remount ro: /sys/fs/cgroup/devices
src/main/tools/linux-sandbox-pid1.cc:265: remount ro: /sys/fs/cgroup/freezer
src/main/tools/linux-sandbox-pid1.cc:265: remount ro: /sys/fs/cgroup/memory
src/main/tools/linux-sandbox-pid1.cc:265: remount ro: /sys/fs/cgroup/rdma
src/main/tools/linux-sandbox-pid1.cc:265: remount ro: /sys/fs/cgroup/hugetlb
src/main/tools/linux-sandbox-pid1.cc:265: remount ro: /sys/fs/cgroup/blkio
src/main/tools/linux-sandbox-pid1.cc:265: remount ro: /sys/fs/pstore
src/main/tools/linux-sandbox-pid1.cc:265: remount ro: /sys/kernel/debug
src/main/tools/linux-sandbox-pid1.cc:265: remount ro: /sys/kernel/config
src/main/tools/linux-sandbox-pid1.cc:265: remount ro: /sys/fs/fuse/connections
src/main/tools/linux-sandbox-pid1.cc:265: remount ro: /proc
src/main/tools/linux-sandbox-pid1.cc:265: remount ro: /proc/sys/fs/binfmt_misc
src/main/tools/linux-sandbox-pid1.cc:265: remount ro: /boot
src/main/tools/linux-sandbox-pid1.cc:265: remount ro: /home
src/main/tools/linux-sandbox-pid1.cc:265: remount rw: /home/david/.cache/bazel/_bazel_david/d028113dbc50ecb39802891af462884e/sandbox/linux-sandbox/1/execroot/__main__
src/main/tools/linux-sandbox-pid1.cc:265: remount rw: /home/david/.cache/bazel/_bazel_david/d028113dbc50ecb39802891af462884e/sandbox/linux-sandbox/1/execroot/__main__
src/main/tools/linux-sandbox-pid1.cc:265: remount rw: /tmp
src/main/tools/linux-sandbox-pid1.cc:265: remount rw: /dev/shm
src/main/tools/process-tools.cc:118: sigaction(32, &sa, nullptr) failed
src/main/tools/process-tools.cc:118: sigaction(33, &sa, nullptr) failed
# runtime/cgo
unknown ptrSize for $GOARCH "wasm"
# os/user
bazel-out/k8-fastbuild/bin/external/io_bazel_rules_go/js_wasm_stripped/stdlib%/src/os/user/lookup.go:11:41: undefined: current
bazel-out/k8-fastbuild/bin/external/io_bazel_rules_go/js_wasm_stripped/stdlib%/src/os/user/lookup.go:32:9: undefined: lookupUser
bazel-out/k8-fastbuild/bin/external/io_bazel_rules_go/js_wasm_stripped/stdlib%/src/os/user/lookup.go:41:9: undefined: lookupUserId
bazel-out/k8-fastbuild/bin/external/io_bazel_rules_go/js_wasm_stripped/stdlib%/src/os/user/lookup.go:47:9: undefined: lookupGroup
bazel-out/k8-fastbuild/bin/external/io_bazel_rules_go/js_wasm_stripped/stdlib%/src/os/user/lookup.go:53:9: undefined: lookupGroupId
bazel-out/k8-fastbuild/bin/external/io_bazel_rules_go/js_wasm_stripped/stdlib%/src/os/user/lookup.go:58:9: undefined: listGroups
GoStdlib: error running subcommand: exit status 2
src/main/tools/linux-sandbox-pid1.cc:437: waitpid returned 2
src/main/tools/linux-sandbox-pid1.cc:457: child exited with code 1
src/main/tools/linux-sandbox.cc:204: child exited normally with exitcode 1
Target //cmd/wasm:wasm failed to build
INFO: Elapsed time: 11.499s, Critical Path: 11.29s, Remote (0.00% of the time): [queue: 0.00%, setup: 0.00%, process: 0.00%]
INFO: 0 processes.
FAILED: Build did NOT complete successfully

```