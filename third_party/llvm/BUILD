licenses(["notice"])

load("//tools:build_rules/cc_resources.bzl", "cc_resources")

package(default_visibility = ["//visibility:public"])

filegroup(
    name = "license",
    srcs = ["LICENSE"],
)

filegroup(
    name = "git",
    srcs = [],
)

cc_library(
    name = "llvm",
    # See https://github.com/google/bazel/issues/61 regarding check_modules's
    # modules_checked_empty.cc.
    # Do not sort; srcs are link-order dependent.
    srcs = [
        "llvm/build/lib64/libclangFormat.a",
        "llvm/build/lib64/libclangToolingCore.a",
        "llvm/build/lib64/libclangTooling.a",
        "llvm/build/lib64/libclangFrontend.a",
        "llvm/build/lib64/libclangDriver.a",
        "llvm/build/lib64/libclangParse.a",
        "llvm/build/lib64/libclangSema.a",
        "llvm/build/lib64/libclangEdit.a",
        "llvm/build/lib64/libclangRewrite.a",
        "llvm/build/lib64/libclangSerialization.a",
        "llvm/build/lib64/libclangAST.a",
        "llvm/build/lib64/libclangLex.a",
        "llvm/build/lib64/libclangBasic.a",
        "llvm/build/lib64/libclangAnalysis.a",
        "llvm/build/lib64/libLLVMMipsInfo.a",
        "llvm/build/lib64/libLLVMAArch64Info.a",
        "llvm/build/lib64/libLLVMARMInfo.a",
        "llvm/build/lib64/libLLVMPowerPCInfo.a",
        "llvm/build/lib64/libLLVMX86Info.a",
        "llvm/build/lib64/libLLVMOption.a",
        "llvm/build/lib64/libLLVMMC.a",
        "llvm/build/lib64/libLLVMMCParser.a",
        "llvm/build/lib64/libLLVMBitReader.a",
        "llvm/build/lib64/libLLVMProfileData.a",
        "llvm/build/lib64/libLLVMCore.a",
        "llvm/build/lib64/libLLVMBinaryFormat.a",
        "llvm/build/lib64/libLLVMSupport.a",
        "llvm/build/lib64/libLLVMDemangle.a",
    ],
    hdrs = glob([
        "llvm/include/**",
        "llvm/build/include/**",
        "llvm/build/tools/clang/include/**",
        "llvm/tools/clang/include/**",
    ]),
    defines = [
        "__STDC_LIMIT_MACROS",
        "__STDC_CONSTANT_MACROS",
    ],
    includes = [
        "llvm/build/include",
        "llvm/build/tools/clang/include",
        "llvm/include",
        "llvm/tools/clang/include",
    ],
    linkopts = [
        "-ldl",
        "-lcurses",
        "-lm",
        "-lpthread",
    ],
    linkstatic = 1,
    deps = [
        "//third_party/zlib",
    ],
    alwayslink = 1,
)

cc_resources(
    name = "clang_builtin_headers_resources",
    data = glob(["llvm/build/lib64/clang/5.0.0/include/**/*.h"]),
)
