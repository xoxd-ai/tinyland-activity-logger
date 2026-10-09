# @tummycrypt/tinyland-activity-logger (retired)

This repository is retired and archived (2026-10-09, estate uplift rulings
RU2, RU6, RU7, RU8).

Its code now lives in
[xoxd-ai/tinyland-logging](https://github.com/xoxd-ai/tinyland-logging) as
the `./activity` subpath export of `@tummycrypt/tinyland-logging`, starting
with tinyland-logging 1.1.0. The API is unchanged: `AdminActivityLogger`,
`getAdminActivityLogger`, `resetAdminActivityLoggerInstance`,
`logAdminAction`, `configureActivityLogger`, `getActivityLoggerConfig`,
`resetActivityLoggerConfig` and the `ActivityLog`, `UserContext` and
`ActivityLoggerConfig` types.

## Migrating

1. In `MODULE.bazel`, replace
   `bazel_dep(name = "tummycrypt_tinyland_activity_logger", ...)` with
   `bazel_dep(name = "tummycrypt_tinyland_logging", version = "1.1.0")`
   from [xoxd-ai/bazel-registry](https://github.com/xoxd-ai/bazel-registry),
   and link `@tummycrypt_tinyland_logging//:pkg` with `npm_link_package`.
2. Change imports from `@tummycrypt/tinyland-activity-logger` to
   `@tummycrypt/tinyland-logging/activity`.

The registry module `tummycrypt_tinyland_activity_logger` is marked
deprecated. Its 0.2.2 and 0.2.3 entries stay resolvable and nothing is
yanked, so existing pins keep building until they move. The package is no
longer published to npm or GitHub Packages; the publish workflow is removed.
