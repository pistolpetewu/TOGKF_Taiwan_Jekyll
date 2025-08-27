source "https://rubygems.org"

# ✅ 用 GitHub Pages 的官方相依組合（確保跟線上環境一致）
gem "github-pages", group: :jekyll_plugins

# ✅ 你用得到的 Jekyll 外掛（由 github-pages 幫你鎖兼容版本）
group :jekyll_plugins do
  gem "jekyll-feed"
  gem "jekyll-seo-tag"
  gem "jekyll-sitemap"
end

# ✅ Windows/本機開發品質提升 & 消除你看到的警告
gem "webrick", "~> 1.8"          # Ruby 3+ 本機 serve 需要
gem "wdm", "~> 0.1", platforms: [:windows]  # 更快的檔案監看（消除 wdm 提示）
gem "tzinfo-data"                # Windows 時區資料
gem "fiddle"                     # 消除 Ruby 3.5 之後的 fiddle 警告
gem "faraday-retry"              # 消除 Faraday 「需要 retry 中介層」提示
