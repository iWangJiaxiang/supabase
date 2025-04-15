<h1 align="center">Supabase UNLOCK [WIP]</h1>

<p align="center">
  <a href="https://github.com/iWangJiaxiang/supabase-unlock">
    <img src="https://github.com/iWangJiaxiang/supabase-unlock/actions/workflows/publish_image.yml/badge.svg?branch=unlock" alt="CI State">
  </a>
  <a href="https://github.com/iWangJiaxiang/supabase-unlock/pkgs/container/supabase-unlock">
    <img src="https://img.shields.io/badge/ghcr.io-iwangjiaxiang/supabase--unlock:latest-blue" alt="CI State">
  </a>
  
</p>

Supabase UNLOCK 是 [SupaBase](https://github.com/supabase/supabase) 的社区维护版，目标是提供和云端相同的功能和体验，从而满足社区用户对 SupaBase 云端功能和体验的需要。  
Supabase UNLOCK is a community-maintained version of [SupaBase](https://github.com/supabase/supabase), aiming to provide the same features and experience as the cloud version, which is needed by self hosted instance.

本项目能够在自托管版本解锁 SupaBase 云的高级功能，并且保持每个示例只有一个项目的设计理念，确保项目之间数据隔离。  
This project unlocks advanced SupaBase cloud features in the self-hosted version while adhering to the design principle of one project per instance, ensuring data isolation between projects.

项目基于官方代码仓库进行修改，仅对前端页面和必要的 API 进行修改，不对任何数据库相关操作进行改动，因此，理论上本项目可以和官方的镜像互相无缝切换。尽管如此，但仍无法保证不会出现 BUG，本项目及维护者不对这些情况负责。  
The project is based on the official code repository, modifying only the frontend pages and necessary APIs without altering any database-related operations. Therefore, in theory, this project can seamlessly switch with the official image. However, bugs may still occur, and this project and its maintainers are not responsible for such issues.

感谢 SupaBase 带来如此优雅且强大的产品。  
Thanks to SupaBase for providing such an elegant and powerful product.

## Unlocked Features

- [ ] Edge Functions
  - [x] UI
  - [ ] API [No codes in repo]
- [x] Authentication
  - [x] UI
  - [x] API [Not fully tested]

## Locked Features

The features what are unnecessary or impossible to unlock.

| Feature | Reason |
| :=: | :=: |
| [Branching](https://supabase.com/docs/guides/deployment/branching) | Not suitable for single instance |
| Feedback | Unnecessary |
| Telemetry | Unnecessary |

## Usage

遵循官方安装说明。  
Follow the official installation instructions.  

将官方镜像 `supabase/studio` 替换成 `ghcr.io/iwangjiaxiang/supabase-unlock`。  
Replace the official image `supabase/studio` with `ghcr.io/iwangjiaxiang/supabase-unlock`.  

选择合适的 TAG，参考[ supabase unlock 镜像页面](https://github.com/iWangJiaxiang/supabase-unlock/pkgs/container/supabase-unlock)。  
Choose the appropriate TAG by referring to the [supabase unlock image page](https://github.com/iWangJiaxiang/supabase-unlock/pkgs/container/supabase-unlock).  

Example command:

```bash
docker pull ghcr.io/iwangjiaxiang/supabase-unlock:latest
```

GO

## Key points

- `IS_PLATFORM` to unlock cloud features
- `isFreePlan` to unlock cloud pro features
- `useOrgSubscriptionQuery` to unlock subscription
- Set api returns single proj / org for self hosted instance
