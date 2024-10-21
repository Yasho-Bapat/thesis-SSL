# Git Hooks

* get started with prototyping something
* sandbox lua hook -- ask patrick

## Notes on how gittuf and targets works
* In gittuf, delegations are used for storing policies

## Thoughts
* Maybe we could have `.gittuf/hooks` where we store the hooks and distribute them from there
* Targets metadata could contain a `hooks` reference or a filepath or a commit hash to them  -- filepath might be a good, straightforward option
* this will allow us to see who made changes to the hooks too, who to credit who to blame
* **Stuff to answer here**
  * What happens when different people need to see/use different hooks?
    * maybe within `.gittuf/hooks` we could have a directory structure where different people can access different hooks
      * For example, `.gittuf/hooks/security`, `.gittuf/hooks/appdev`, etc.
      * And then in the Targets metadata, reference the directory above, or a commit hash (not sure about the commit hash tbh)
      * the directory can be baseX encoded to keep the hook field in the metadata constant sized.
      * THIS WON'T WORK
    * Use git repository keys to ensure identity
* Possible solution:
  * Have a `.gittuf/hooks` directory to store hooks and distribute them
  * Add a `Hooks` field to the Targets metadata which has `HooksPath` and `keyIDs`. `keyIDs` will be an array of keys, which will be all the keys which need to run a hook
  * Have a `hooks.json` metadata file which contains the following:
    * `stage` to signify when the hook should be run
    * `filename` to signify which file should be run at the associated stage
    * `keyIDs` to signify which keys should run this file