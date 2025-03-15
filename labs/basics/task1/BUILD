load("@rules_qt//:qt.bzl", "qt_cc_binary", "qt_cc_library")

qt_cc_library(
    name = "main_window",
    srcs = [ "dummy.cpp" ],
    hdrs = [
        "mainwindow.h",    # Ensure these files exist
        "MyWindow.h",       # and contain Q_OBJECT macros
        "QuestionManager.h",
        "QuestionView.h",
        "Ticket.h",
        "GoodDelegate.h",
    ],
defines = ["QT_NO_KEYWORDS"],  # Disable Qt keyword macros

    deps = [
        "@rules_qt//:qt_widgets",
        "@rules_qt//:qt_core",
        "@rules_qt//:qt_gui",
    ],
)

qt_cc_binary(
    name = "mainwindow",
    srcs = ["main.cpp"],  # Only contains `main()`, includes headers
        defines = ["QT_NO_KEYWORDS"],  # Also add here if needed

    deps = [
        ":main_window",
        "@rules_qt//:qt_core",
        "@rules_qt//:qt_widgets",
    ],
)