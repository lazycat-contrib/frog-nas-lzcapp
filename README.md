# 旅行青蛙 (LazyCat)

《旅行青蛙·中国之旅》离线安卓包移植的 NAS 网页应用，打包为 LazyCat LPK v2。上游：[Kasbuky-sudo/frog-nas](https://github.com/Kasbuky-sudo/frog-nas)（镜像 `heizicao/frog-nas`）。

> 非商业性游戏保存与研究项目，基于《旅行青蛙》（原著作权人：Hit-Point Co., Ltd.）制作。

## 部署信息

- **包名**：`cloud.lazycat.app.frog-nas`
- **版本**：跟随上游镜像 tag 自动更新（每日 UTC 03:17 检查）
- **交付模式**：mirror（镜像引用 + digest 校验）
- **min_os_version**：1.5.0

## 入口

- **主界面**：`/`（旅行青蛙游戏页）
- **管理后台**：`/admin`

## 关键配置

- `PUBLIC_URL=${LAZYCAT_PUBLIC_URL}`：推送明信片使用正确的对外绝对链接
- `FROG_FAITHFUL=1`：引擎时长开关（默认开）
- 数据持久化：`/lzcapp/var/data:/app/data`
- 发布：仅喵喵商店

## 文件结构

```
package.yml              # 包元数据（含多入口本地化）
lzc-manifest.yml         # 运行结构（entries + upstreams + frog 服务）
lzc-build.yml            # 构建配置
icon.png                 # 应用图标
.github/lazycat-action.yml      # Action 配置（镜像源 / mirror 交付 / 喵喵商店）
.github/workflows/lazycat.yml   # 发布工作流
```
