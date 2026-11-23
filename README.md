# EasyAPI 上架发布站点

> 本仓库**只包含对外公开内容**：隐私政策、用户支持页、上架文案。
> **不含** App 源码、签名证书、AppKey 或任何内网信息，可安全公开。

## 一、这个仓库是做什么的

App Store 上架时有两个**必填的公网链接**：

| App Store Connect 字段 | 本仓库对应地址 |
|---|---|
| 隐私政策 URL | `https://terryzou1989.github.io/easy-api/privacy-policy.html` |
| 用户支持 URL | `https://terryzou1989.github.io/easy-api/` |

GitHub Pages 把这个仓库变成免费、稳定、公网可访问的静态网站，用来承载这两个页面。

## 二、目录内容

| 文件 | 用途 |
|---|---|
| `index.html` | 用户支持页（站点首页）— App Store 用户支持 URL 指向它 |
| `privacy-policy.html` | 隐私政策 — App Store 隐私政策 URL 指向它 |
| `ASO文案.md` | 名称 / 副标题 / 关键词 / 描述 / 促销文字（填 App Store Connect 用） |
| `截图宣传语设计.md` | 6 张截图的取景页面 + 主副标题（制作截图用） |
| `.nojekyll` | 让 Pages 直接发布静态文件，无需修改 |
| `README.md` | 本说明 |

> 页面之间全部使用相对链接（`index.html` ↔ `privacy-policy.html`），改仓库名也不用改代码。
> `ASO文案.md` 和 `截图宣传语设计.md` 是运营素材，公开无妨；若只想公开两个网页，删掉这两份即可。

## 三、开启 GitHub Pages（一次性设置）

仓库已在本地初始化，`origin = https://github.com/TerryZou1989/easy-api.git`。

1. 先把文件推送上去（见下一节）
2. 打开 `https://github.com/TerryZou1989/easy-api` → **Settings** → 左侧 **Pages**
3. Build and deployment：
   - Source：**Deploy from a branch**
   - Branch：**main** / **/(root)**
4. 点 **Save**，等 1~2 分钟
5. 出现绿色提示 **Your site is live at https://terryzou1989.github.io/easy-api/** 即成功

## 四、推送文件到 GitHub

```bash
cd /c/Users/admin/Documents/GitHub/publish/easy-api
git add .
git commit -m "Add EasyAPI App Store public pages"
git push -u origin main
```

> 首次 push 若要求登录，GitHub 已停止用账号密码，需用 **Personal Access Token**（Settings → Developer settings → Personal access tokens → Tokens(classic)，勾选 `repo`）。把 token 当作密码输入即可。

## 五、把 URL 填进 App Store Connect

| App Store Connect 字段 | 填写内容 |
|---|---|
| 隐私政策 URL | `https://terryzou1989.github.io/easy-api/privacy-policy.html` |
| 用户支持 URL | `https://terryzou1989.github.io/easy-api/` |

填完后浏览器打开两个地址自查：能看到 EasyAPI 的隐私政策和支持页即可。

## 六、公开前安全核对

- [x] 无 App 源码（`.vue` / `.js` / `.json` 配置等）
- [x] 无 `keystore` / 私钥 / AppKey / 证书
- [x] 无内网地址、测试 token、数据库账号
- [x] 唯一公开的邮箱 `terryzou1989@163.com` 是**希望用户联系**的开发者邮箱，公开无妨

## 七、后续更新

以后改了网页内容，push 上去后 Pages 会在 1~2 分钟内自动更新，URL 不变，无需在 App Store Connect 改任何东西。

## 八、哪些东西不要放进这个仓库

主项目的这些内容**严禁**上传到这里（会泄露源码或密钥）：

- `app/` 下的任何 Vue / JS 源码
- `android-offline/`、`ios-offline/` 以及签名证书、keystore、AppKey
- `docs/` 里含内部流程的文档（如 `iOS-AppStore上架准备清单.md`）
- 任何 `.env`、token、私钥文件
