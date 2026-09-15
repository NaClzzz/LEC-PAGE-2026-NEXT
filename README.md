# LEC 2026 招新页（Next.js 版）

由 lec-recruit-2026（React + TypeScript + Vite 单页应用）1:1 迁移到 Next.js（App Router）的版本，页面内容、视觉与交互保持一致。

技术栈：Next.js 16 + React 19 + TypeScript + Tailwind CSS v4 + GSAP + Lenis

现已完成静态“团队动态”与“往届成员”

## 与 Vite 版的主要差异（仅入口层）

- 单页入口改为 `src/app/page.tsx`，SEO meta / og / Bing、百度站点验证移至 `src/app/layout.tsx` 的 `metadata`
- 字体（Google Fonts + MiSans CDN）`<link>` 保留在 `layout.tsx` 中
- 全部交互组件标注 `'use client'`；`GridMotion` 因强依赖 `window`，改为挂载后渲染
- 二维码路径由 `import.meta.env.BASE_URL` 改为 `/qr.png`

## 开发

```bash
pnpm install
pnpm dev      # http://localhost:3000
pnpm build    # 生产构建（/ 为完全静态预渲染）
pnpm start
```

部署在 vercel：https://lec-page-2026.ziroo.cn/
