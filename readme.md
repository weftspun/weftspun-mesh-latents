# weftspun-mesh-latents

The goal manifest for **corpus, and mesh latents** — everything that turns an image into
geometry: TRELLIS2 and its VAE, P3SAM, Pixal3D, VoxHammer, and the embedders that index what
they make.

```
repo init -u https://github.com/weftspun/weftspun-mesh-latents.git
repo sync
```

## What this repository is, and what it is not

It is `default.xml` and this file. There is no code here, and that is the point: a manifest
that also held source would be a place for a project to sit without being placed on a side.

`default.xml` is the **placement authority** for the 44 projects it lists. A repository sits on
a side of the hexagon because this file says so, and a repository this file does not name is
unplaced — which is the drift the six words exist to stop. The working agreements state the
rule; they arrive at the workspace root through the two `linkfile` entries on the `logbook`
project, so `CLAUDE.md` and `AGENTS.md` are two names for one tracked file rather than copies
that drift.

## The split, and why the counts overlap

This manifest was split out of `weftspun/weftspun`, which is now **archived**. Two goal
manifests replace it:

| manifest | projects | goal |
|---|---|---|
| `weftspun/weftspun-mesh-latents` | 44 | corpus, and mesh latents |
| `weftspun/weftspun-keypoint` | 51 | corpus, and 104-keypoint wholebody detection |

**20 projects appear in both**, and the duplication is deliberate rather than an artefact of
the split. The corpus is shared rather than copied: `dataflow-coco-gemx`, `coco-ood-eval`, the
CC0 asset stages, `logbook`, `request-for-discussion` and `.github` serve both goals, so both
manifests name them and both render from the same assets into the same logbook. A project that
serves one goal and not the other is the exception here, not the rule.

The measurement, taken rather than assumed: 51 and 44 projects, 20 shared, 24 named by this
manifest alone.

One consequence worth stating rather than discovering. The archived manifest still lists its
projects and always will, because an archive is read-only, not empty. So placement is what a
**live** goal manifest says — a project inherited only from `weftspun/weftspun` reads as placed
and is not.

## Sides

| side | projects |
|---|---|
| `1-transport` | 7 |
| `2-contract` | 3 |
| `3-interactor` | 19 |
| `4-entities` | 1 |
| `6-datasource` | 9 |
| `7-service` | 1 |

Four projects check out to dotted paths rather than a side — `.logbook`,
`.request_for_discussion`, `.tropes_removal_model` and `.github`. They are workspace
infrastructure rather than a stage in the pipeline, and the leading dot keeps them out of the
numbered ordering without hiding them from `repo status`.

Note `5-` is absent, here and in `weftspun-keypoint` alike — neither manifest names a project
under it. So the gap is in the naming rather than in this checkout: nothing failed to sync.

## Adding a project

A `<project>` entry, on a side, with a pinned `revision`, added when the repository is created
rather than later. Third-party dependencies come in the same way — **git submodules are
blocklisted**, because a submodule pins a dependency in a file only `git` reads, where
`repo status` cannot see it and a bump appears as a bare hash with no name, branch or reason.
A manifest entry answers what version, from where, and why, because a comment can sit beside
it.

Fork before you pin: a `revision` on somebody else's repository is a promise they have not
made.
