# pvz-vanilla-recon
Based on PvZ Updated Base, vanilla-recon aims to negate every visual and functional inconsistency and bug that Updated Base features, without adding anything new to the original PvZ.

The goal here is to make the Updated Base reconstruction as close as possible to vanilla OG PvZ.
This means that there will be **no new features, enhancements, or any sort of change to the gameplay.** (apart from when fixing bugs and inconsistencies)

This creates the perfect choice for a clean reconstruction of PvZ that misses out on the bloat that many other reconstructions have. (most, if not all, using const variables instead of `#IFDEF`s, which bloats the exe file size even more.)

>[!NOTE]
vanilla-recon's model version of PvZ is 1.0.0.1051 (Plants vs. Zombies Original PC Edition) (This is NOT Game Of The Year Edition)

# 'VANILLA_FIX'
Every fix or change that's been made to the code is (maybe not thoroughly T_T) explained through comments with the keyword `VANILLA_FIX`.

This makes finding my edits WAY easier. By using CTRL+SHIFT+F to search for `VANILLA_FIX`, you'll be able to quickly find everything I've done, meaning you can easily apply them to your own mods without having to switch!

Example Fixes:
```c++
int aSeedRecharge = mApp->mSeedPacket->GetSeedRecharge(theSeedType); //--VANILLA_FIX: Use GetSeedRecharge() instead of GetPlantRecharge().

if (aSeedRecharge <= 30) //--VANILLA_FIX: Changed 40 to 30
{
  theRechargeString = _S("very fast");
}
else if (aSeedRecharge <= 70) //--VANILLA_FIX: Changed this 'if' into an 'else if'
{
  theRechargeString = _S("fast");
}
else //--VANILLA_FIX: Added 'else' statement to not override theRechargeString with _S("slow") anyway.
{
  theRechargeString = _S("slow")
}
```

## What's been fixed so far?
Many, many changes have been made to come closer to original PvZ. These changes fix and prevent:
- Zen Garden's buttons not moving to the far left when gaining every Zen Garden item.
- Upwards moving rain.
- Completely broken Upsell.
- 'Watery Graves' related inconsistencies (such as hihats being enabled when the track starts).
- Being able to click on hidden zombies in the almanac.
- Swapped around highlighted and non-highlighted challenge buttons.
- Completely inaccurate CYS.
  - Incorrect font for LET'S ROCK!
  - Scrolling code added by god knows who!?
  - Seed flying back to chooser animation not playing.
- Intro's camera moving from right to left.
- Zombies' random speed having a slightly lower max value.
- Gatling-Pea zombie's projectile not accounting for the zombie's altitude.
- Incorrect main_icon, featuring less colours shown in the taskbar.
- Gatling-Pea unlocking after completing Adventure mode.
- And many, many more!

## Questions & Answers
### Q: Has modding / the workflow been made any different?
A: Nope! Vanilla-recon is built to keep the simplicity of modding standard reconstructions while providing the extensive list of bug fixes that more complex reconstructions have.\
Modding with vanilla-recon is no different to modding with Updated Base, Quality Enhanced, LawnTweaks, meaning the recon is more accessible and easy to use without any extra steps at all.
### Q: I would like for (.....) to be added, could you do that?
A: It depends, but most-likely no.

Features present in vanilla-recon are meant to be kept in-line with OG PvZ. Meaning extras that other reconstructions may have such as Quick-Play, 2X Speed Button and Zombatar will not be added.
This includes bugs and unintended issues that OG PvZ has, such as hypnotized zombotanies shooting backwards, meaning they too will not be fixed.
### Q: Why should I use this?
A: Some modders prefer a clean-slate to work on, vanilla-recon gives just that.
### Q: Where can I report a bug (that OG PvZ also has)?
A: I'm sure you can do it here in GitHub Issues (if I remember correctly) though I'm still not that experienced in it so be patient please :)

# Credits
### Main
- [@person6423_](https://github.com/person6423) - Project Creator, Lead Programmer
### Special Thanks
- [@Electr0Gunner](https://github.com/Electr0Gunner) - Additional Fixes, Creator of [ResoddedFramework](https://github.com/LawnProject/ResoddedFramework) which was a great help
- [@InLiothixi](https://github.com/InLiothixi) - Additional Fixes, Creator of [Stable-Decompile](https://github.com/InLiothixi/Stable-Decompile) which was a great help
- [@verse090](https://github.com/verse090) and [@cardbored-code](https://github.com/cardbored-code) - Name of the project <sub>(they both also came up with, soon to be released, 'chocolate-recon' :shushing_face:)</sub>
- Original authors of the 0.9.9 decompilation
- Modders that touched up and created Updated Base
### Acknowledgements
- PopCap Games - Plants vs. Zombies Franchise, SexyAppFramework Engine
