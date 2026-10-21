# Retro Rewind updater

Checks the official Retro Rewind feed every six hours and rebuilds both browser engines when a new pack is available. Successful verified builds publish to https://retro-rewind-web.ljste.workers.dev/.

Only the automation definition and its monthly health record live in this public repository. Application source is checked out from a separate private repository with a read-only deploy key. No engine binaries, original game assets, saves, account data, or credentials are committed or uploaded as Actions artifacts.

Standard public Linux runners do not consume private-repository Actions minutes. Actions is disabled on the private source repository. The account has a $0 paid Actions spending cap. The input cache remains below the included 10 GB limit; cache eviction causes a fresh verified download. No paid runners or artifact storage are used.

The monthly health commit prevents GitHub from disabling the schedule after 60 days without repository activity. GitHub may delay scheduled runs. Failed builds leave the current site in place and appear in Actions notifications.

Use **Actions > Update Retro Rewind > Run workflow** for an immediate check. Enable **force** to rebuild the current pack. The [full hosted build and publication](https://github.com/ljste/retro-rewind-updater/actions/runs/39532227586) passed, and the [follow-up check](https://github.com/ljste/retro-rewind-updater/actions/runs/39533502724) correctly skipped an unchanged pack.
