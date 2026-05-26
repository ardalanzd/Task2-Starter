# Number Guessing Game

## Branch Structure

- **main** - Stable production branch. Contains the base number guessing game.
- **dev** - Integration branch. Adds an encouraging message for players.
- **feature1** - Adds ability to quit game with negative number, play-again loop, and improved feedback messages.
- **feature2** - Adds max attempts limit and game over condition.
- **feature3** - Adds a hint system that shows proximity after 3 attempts.
- **hotfix** - Fixes randomInt to properly include max value in range.

# Number Guessing Game

## Branch Structure

- **main** - The stable version of the game. This is what you would ship to users.
- **dev** - Our main working branch. Features get merged here after testing.
- **feature1** - Added the ability to quit by entering a negative number, plus a play-again loop so you don't have to restart the program.
- **feature2** - Added a max attempts limit (10 tries) so the game actually ends if you can't guess the number.
- **feature3** - Added a hint system that gives you proximity clues after 3 failed attempts.
- **hotfix** - Fixed a bug where the random number generator wasn't including the max value in its range.

## Learning Summary

### Merge vs Rebase vs Squash vs Cherry-pick

**Merge** is the straightforward one. You just combine two branches and Git creates a merge commit that shows both histories. It's honest about what happened — you can see exactly where branches split and came back together. We used this for feature1.

**Rebase** is cleaner but a bit trickier. Instead of creating a merge commit, it replays your commits on top of another branch like they were always there. The history looks linear and easy to read. We used this for feature2. The downside is you shouldn't rebase branches other people are working on — it rewrites history and causes problems for everyone else.

**Squash** was probably the most satisfying one to use. Feature3 had four commits with messages like "done" and "had to fix" which tell you nothing. Squashing lets you combine all of them into one clean commit with a proper message before merging into dev. Much easier to read later.

**Cherry-pick** is useful when you just need one specific commit somewhere without bringing in everything else. We used it to apply the hotfix directly to main without merging all of dev into it.

### What I noticed in the history

With feature1 (merge), you can clearly see the branch split and rejoin in the graph. With feature2 (rebase), the history looks like everything happened in a straight line — cleaner but you lose the visual of where the branch was. Feature3 showed the biggest difference — going from four meaningless commit messages down to one that actually describes what changed.

### When I would use each one

- **Merge** when working with teammates on shared branches — safer and more transparent.
- **Rebase** when I'm working alone on my own feature branch and want a clean history before merging.
- **Squash** whenever I've made a bunch of small "work in progress" commits that don't need to be in the final history.
- **Cherry-pick** for urgent fixes that need to go to a specific branch without a full merge.
