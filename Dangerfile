github.dismiss_out_of_range_messages({
    error: false, # エラーは追加・変更していないコードでもコメント
    warning: true,
    message: true,
    markdown: true
    })
    `find . | grep "TEST-*"`.split("\n").each do |path|
        junit.parse(path)
        junit.report
    end

    android_lint.gradle_task = "app:lint"
    android_lint.report_file = "app/build/reports/lint-result.xml"
    android_lint.filtering = true
    android_lint.filtering_lines = true
    android_lint.lint(inline_mode: true)


    # Warn when there is a big PR
    warn('a large PR') if git.lines_of_code > 500
