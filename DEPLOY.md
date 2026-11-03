# 宿命大战 · 隐私政策站点

本目录是一份**纯静态网站**，只包含隐私政策页面与下载文件，无后端、无外部依赖，任何静态托管都能直接使用。

## 文件说明

| 文件 | 用途 |
|---|---|
| `index.html` | 站点首页（手机 / 电脑自适应，带目录导航） |
| `privacy-policy.html` | 与首页内容相同，兼容旧链接 |
| `privacy-policy.pdf` | 隐私政策 PDF（10 页） |
| `sushengdazhan-privacy-policy.docx` | 隐私政策 Word 版，可直接下载 |
| `404.html` | 404 页面 |
| `robots.txt` | 允许所有搜索引擎收录 |
| `.nojekyll` | GitHub Pages 用，防止 Jekyll 处理 |
| `启动本地预览.cmd` | 双击在本机预览（http://127.0.0.1:8123/） |

## 部署到公网（任选一种，10 分钟内可完成）

### 方案 A：GitHub Pages（免费）
1. 注册 / 登录 GitHub，New repository，名称如 `sushengdazhan-privacy`，设为 **Public**
2. 把本目录**全部文件**拖进仓库（Add file → Upload files → Commit）
3. 仓库 Settings → Pages → Build and deployment → Source 选 **Deploy from a branch** → Branch 选 `main` / `/ (root)` → Save
4. 约 1 分钟后得到：`https://你的用户名.github.io/sushengdazhan-privacy/`
5. 建议把该地址填到 TapTap 开发者后台的「隐私政策链接」

> 国内访问 GitHub Pages 有时较慢，若审核方打不开，优先用方案 B / C 并绑定已备案域名。

### 方案 B：阿里云 OSS（国内访问快）
1. 控制台 → 对象存储 OSS → 创建 Bucket：读写权限选 **公共读**，地域选离你近的（如华北2·北京）
2. 进入 Bucket → 基础设置 → **静态页面**：默认首页填 `index.html`，默认 404 页填 `404.html`
3. 上传本目录全部文件（保留目录结构）
4. 访问 `https://<bucket名>.oss-cn-beijing.aliyuncs.com/index.html` 即可
5. 上架/备案建议绑定自有域名并完成 ICP 备案，得到 `https://yuming.com/` 形式的链接

### 方案 C：腾讯云 COS（国内访问快）
1. 控制台 → 对象存储 → 创建存储桶：访问权限 **公有读私有写**
2. 存储桶 → 基础配置 → **静态网站**：开启，索引文档 `index.html`，错误文档 `404.html`
3. 上传全部文件 → 用「静态网站」域名访问
4. 同样建议绑定已备案域名

### 方案 D：Gitee Pages
1. 注册 Gitee（需实名）→ 新建仓库 → 上传全部文件
2. 仓库 服务 → Gitee Pages → 部署（该服务规则可能变化，以页面提示为准）

## 填到 TapTap 开发者后台

1. 登录 [TapTap 开发者中心](https://developer.taptap.cn/) → 选择游戏 → 商店信息 / 上架资料
2. 找到「**隐私政策链接**」，填入你部署得到的 `https://...` 地址（不要填 127.0.0.1）
3. 确认该链接**无需登录、可直接打开**；审核会点开检查内容与包体实际行为是否一致

## 修改内容后如何更新

1. 改 Word 版：`宿命大战隐私政策-TapTap完整版.docx`
2. 重新生成站点：运行 `python build_taptap_policy.py`（在 D:\deepseek 下）
3. 把 `privacy-site` 里的文件重新上传覆盖即可

## 审核自查清单

- [ ] 首启隐私弹窗：**同意 / 不同意** 双按钮，不默认勾选；拒绝后不请求任何权限、不收集任何信息
- [ ] 游戏内提供「隐私设置 / 撤回同意」入口，与政策第六条描述一致
- [ ] 政策中的权限表 = `AndroidManifest.xml` 实际权限
- [ ] 政策中的 SDK 表 = 包体实际集成的 SDK（含用途、收集字段、隐私政策链接）
- [ ] 注销账号入口真实可用，路径与政策一致
- [ ] 客服电话 / 邮箱真实可达，15 个工作日内响应
