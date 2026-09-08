# AGENTS.md


## Organization-Wide Finish-First Workspace Policy

This policy is mandatory for every human and agent working in this repository.

- Leave the repository, its worktree registry, branches, and runtime files in a better state than you found them. Finish admitted work before starting more.
- The normal maximum is **three total local worktrees/checkouts per repository**, including the primary checkout, and **three active non-default branches/workstreams**. Resource, conflict, or host limits may reduce this. Exceeding it requires a recorded owner, concrete concurrent purpose, recovery/finish action, and expiry; nested agents or worktrees never bypass the limit.
- Before creating a branch, worktree, or checkout, fetch the remote default branch and audit existing registered and external worktrees. Reuse, finish, or retire an existing lane when safe. Do not create standalone duplicate clones when a Git worktree will do.
- Prefer useful completion in this order: eligible cleanup, review-ready delivery, unblockable active work, then new work. A completed useful increment should be accepted and merged into the default branch before its workspace is released; link remaining scope to a successor milestone or issue.
- A genuinely blocked effort may be paused without occupying local capacity only after its valuable state is committed and pushed to a named branch, its blocker/owner/next action is recorded, and its local workspace is clean and recoverable. Never merge incomplete or failing work merely to reclaim a slot.
- After a Sam-owned PR merges, promptly fetch the default branch; verify the candidate, merge result (including squash/rebase variants), validation/release evidence, cleanliness, ownership, active executions, and runtime dependencies; then remove the eligible worktree through Git, delete its merged local and remote source branches, and prune stale metadata.
- Before any deletion, discover worktrees through Git (including external paths) and recheck exact `HEAD`, merge evidence, tracked/untracked changes, process activity, and runtime dependencies. Dirty, unmerged, ambiguous, active, runtime-dependent, or another person's work stays protected with an explicit disposition.
- Every PR review finding, including outdated or merged-PR threads, needs an explicit public reply with the disposition and validation before resolution. Do not make anyone infer whether feedback was handled.
- Report only measured storage reclaimed from filesystem capacity changes. Cleanup is operational hygiene, not delivery credit; do not invent or game metrics.



## Parent Workspace Directory Hygiene (Required)

This policy is mandatory for every human and agent working in this repository.

- Treat every workspace parent directory—shared roots such as `/Users/sam/git/crucible`, dedicated `_worktrees/`, repo-local `.worktrees/`, and temporary workspace roots—as a bounded execution queue, never an archive. A parent may retain only the primary checkout and the repository's bounded active lanes; task-named clone copies, empty temporary roots, orphaned directories, and stale metadata are cleanup work, not harmless background state.
- Before admitting work and after every merge, abandonment, or recovery, enumerate the parent directory's direct children and compare them with Git's registered worktrees, including external paths. `git worktree prune` alone is insufficient: it repairs metadata but does not remove the physical directories consuming storage or creating Finder noise.
- Remove an eligible registered worktree through its owning Git worktree interface, then remove its merged local and remote source branches and prune metadata. For an independent clone in a shared parent, require the same proof of clean, inactive, Sam-owned, validated merged work and confirm it does not contain a protected nested worktree before removing the actual clone directory. Do not leave an eligible clone directory behind merely because it is unregistered.
- Before deleting any parent directory, inspect nested worktrees, tracked and untracked changes, process activity, runtime dependencies, ownership, and recovery value. If a parent contains a dirty, unmerged, ambiguous, active, runtime-dependent, or another person's child, preserve that child and parent with a named branch plus recorded owner, blocker, and next action; do not destroy the parent merely because its own checkout is clean.
- After an eligible parent's last child has been removed, remove the now-empty dedicated temporary parent as well. Never delete a broad shared root such as `/Users/sam/git/crucible`; instead leave it with only the deliberately retained primary repositories and bounded active lanes.
- Unregistered non-Git children may not be swept blindly. Identify their owner and contents, preserve valuable evidence where required, and record a concrete disposition before removal. Do not create a new sibling worktree merely to evade an existing protected child.
- Report parent-root hygiene with factual direct-child counts, protected exceptions, and filesystem-capacity deltas measured before and after cleanup. Do not substitute Git registry counts, branch counts, or estimates for physical storage recovery.
