

Hi guys! Before, i found something in the jailbroken DPT-RP1.  
https://www.mobileread.com/forums/showthread.php?t=293735

Now, I pull out the FactoryReset.pkg and some scripts.  
(FactoryReset.pkg, start_eufwupdater.sh, dec.key, sig.key)

It means that, we could likely modify the .pkg file and make an upgrade.

For now, I can unpack the .pkg file, the problem is how to rebuild a modified .pkg?

Unpack command:
```Bash
start_eufwupdater.sh FactoryReset.pkg out out/sig.key out/dec.key
```

If you run it directly, may get an error likes this:
```Bash
./start_eufwupdater.sh: 50: ./start_eufwupdater.sh: arithmetic expression: expecting primary: ""
```

It’s about the problem of anim section, remove anim stuff in the start_eufwupdater.sh, we don’t need it.
Just delete the whole of this part:
```Bash
########################################
# start animation for package check
########################################
```

And then run the command again
```Bash
start_eufwupdater.sh FactoryReset.pkg out out/sig.key out/dec.key
```

Or you can run the script which I have remove the anim stuff
```Bash
start_eufwupdater2.sh FactoryReset.pkg out out/sig.key out/dec.key
```

Finally, you can get some files in the “out” folder  
(FwUpdater  aes256.key  iv  sig.dat)  
The “FwUpdater” folder contains the resources.


So,the problem now, is how to rebuild the resources back into a .pkg?

Welcome to discuss in the issue, or in mobileread forums:    
https://www.mobileread.com/forums/showthread.php?t=294134

My email: hadesome1@gmail.com  
My skype: https://join.skype.com/invite/JPNMlTtXodmB
