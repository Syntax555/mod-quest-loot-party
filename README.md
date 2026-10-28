# Quest Loot Party

Quest Loot Party makes naturally dropped, normal-quality quest loot available
individually to eligible party members. This native AzerothCore module is
included in [AzerothCore Playerbots Portable](https://github.com/Syntax555/mod-playerbots-portable).
Players and bots still need the quest, loot eligibility and bag space; the
module does not create a missing drop or complete a quest.

## Install

Use the assembly's [Latest release and setup guide](https://github.com/Syntax555/mod-playerbots-portable#quick-start)
for a playable Windows server. The module is included and enabled; no client
addon is required.

For a native build, follow the assembly's
[build guide](https://github.com/Syntax555/mod-playerbots-portable/blob/main/docs/building.md).
Its [dependency lock](https://github.com/Syntax555/mod-playerbots-portable/blob/main/versions.lock.json)
selects this fork's tested `master` commit and matching core/modules. Rebuild
worldserver after native changes.

## Behavior and configuration

The module marks normal-quality items in the core's quest-loot list as
individually lootable. Drop chances and counts, quest need, item conditions,
faction restrictions and normal looting checks remain the core's responsibility.
Other item qualities and ordinary non-quest loot keep their normal rules.
No gold, progression credit, teleports or mailed rewards are added.

Edit `configs/modules/mod-quest-loot-party.conf` with the portable server stopped.
The native template is [conf/mod-quest-loot-party.conf.dist](conf/mod-quest-loot-party.conf.dist).

| Setting | Portable default | Native template | Purpose |
| --- | --- | --- | --- |
| `QuestParty.Enable` | `true` | `true` | Enable quest-loot sharing |
| `QuestParty.Message` | `false` | `true` | Show the module's login message |

Sharing does not guarantee every quest drop. Each member must loot normally and
qualify for the item. See the assembly's
[party-loot integration](https://github.com/Syntax555/mod-playerbots-portable/blob/main/docs/adaptations.md#playerbots-and-group-play)
for bot looting and roll behavior.

## Source, contributions and license

Maintained in [Syntax555/mod-quest-loot-party](https://github.com/Syntax555/mod-quest-loot-party),
from [pangolp/mod-quest-loot-party](https://github.com/pangolp/mod-quest-loot-party).
The [imported upstream source](https://github.com/pangolp/mod-quest-loot-party/tree/c3955915c76d5a22a9d25a44482345d368a8de82)
contains no README. AzerothCore's original source notices are retained.

Read [AGENTS.md](AGENTS.md) and the assembly's
[contribution workflow](https://github.com/Syntax555/mod-playerbots-portable/blob/main/CONTRIBUTING.md)
before changing this fork. Native builds and release integration run in the
assembly. Licensed under [GNU AGPL v3](LICENSE); source files retain their
AzerothCore copyright notice.
