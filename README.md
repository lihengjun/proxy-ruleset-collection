# proxy-ruleset-collection

Daily-synced collection of upstream proxy rulesets (Surge / Clash / Mihomo).

## Upstream sources

| Subdir | Upstream | Branch |
|---|---|---|
| `sukkalab/` | [SukkaLab/ruleset.skk.moe](https://github.com/SukkaLab/ruleset.skk.moe) | `master` |
| `metacubex/` | [MetaCubeX/meta-rules-dat](https://github.com/MetaCubeX/meta-rules-dat) | `release` |
| `hackl0us/` | [Hackl0us/GeoIP2-CN](https://github.com/Hackl0us/GeoIP2-CN) | `release` |

## Sync mechanism

`.github/workflows/sync.yml` runs daily at `00:00 UTC` (and on manual `workflow_dispatch`). Each run shallow-clones each upstream and replaces the corresponding subdir verbatim. No upstream changes → no commit.

If an upstream repo disappears or is taken down, this collection retains the last successful snapshot until manually pruned.

## Client URL pattern

Direct raw:

```
https://raw.githubusercontent.com/lihengjun/proxy-ruleset-collection/main/<sukkalab|metacubex|hackl0us>/<path>
```

Via jsdelivr CDN (faster + higher rate limit):

```
https://cdn.jsdelivr.net/gh/lihengjun/proxy-ruleset-collection@main/<sukkalab|metacubex|hackl0us>/<path>
```

## License

This repo is a collection / mirror — original content rights belong to each upstream author. Check each subdir for its own license.
