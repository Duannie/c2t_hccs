# c2t_hccs

Kolmafia script to handle a seal clubber community service run with my set of skills and IotMs.

This is a fork of Zdrvst's hccs script, it is a glorious mess of a script made possible when I Dr. Frankensteined bits of codes from many other CS scripts.

This is a continual work-in-progress. It is not likely to run out-of-the-box for most, but others may be able to glean things from it. To see what is needed to run smoothly without changes, see: https://cheesellc.com/kol/profile.php?u=Duan

## Usage

* The main script is `c2t_hccs.ash`, and is the thing that should be run to do a community service run
* Not likely to run out-of-the-box for most.
* Will abort when a non-coil test does not meet its turn threshold after preparations for it are done, which defaults to 1 turn
* Pre-Valhalla: put asdon martin in the workshed
* In Valhalla:
    - Choose Seal Clubber
    - Choose the corresponding "knoll" moonsign
    - Optimal astral stuff is astral six-pack and astral pet sweater, though neither is strictly required
* The script uses mood `hccs-mus` for leveling purposes. So set your own to what you want for what skills you have, otherwise you won't have many buffs while levelling.
    - Exception: the script will cast and handle stevedave's shanty of superiority and ur-kel's aria of annoyance, so either put them in the mood as well or leave 2 song slots open for them
    - The moods I use can be seen in [mood examples.txt](https://github.com/c2talon/c2t_hccs/blob/master/mood%20examples.txt) to use as a starting point.

## User-defined properties the script uses

These are set via the gCLI. Basically so people don't have to edit the script itself to change some simple, but critical, things.

`set c2t_hccs_haltBeforeTest = false`
* Setting this to `true` will cause the script to always halt after prepping for a test, but before doing the test.
* Defaults to `false`

`set c2t_hccs_printModtrace = false`
* Setting this to `true` will cause the script to print the modtrace for the corresponding mods that the test uses before doing the test.
* Defaults to `false`

`set c2t_hccs_joinClan = 90485`
* This is the clan that the script will join for the VIP lounge and fortune teller
* Takes an `int` or `string`, where `int` would be clanid (preferred), and `string` would be the clan name
* Defaults to `90485` (Bonus Adventures From Hell)

`set c2t_hccs_clanFortunes = CheeseFax`
* This is the name of the person/bot that you want to do the fortune teller with
* Defaults to `CheeseFax`

`set c2t_hccs_skipFinalService = false`
* If this is set to `true`, the final service will be skipped leaving you in-run once finished
* Defaults to `false`

`set c2t_hccs_thresholds = 1,1,1,1,1,1,1,1,1,1`
* These are the 10 thresholds corresponding to the minimum turns to allow each test to take
* The script will stop just before doing a test if a threshold is not met after doing all the pre-test stuff
* The order is hp,mus,mys,mox,fam,weapon,spell,nc,item,hot
* Example: `1,1,1,1,35,1,31,1,1,1` will allow the familiar test to take 35 turns, the spell test to take 31 turns, and all others must be 1 turn
* Defaults to `1,1,1,1,1,1,1,1,1,1`

## IotM

The script assumes several IotM are owned and will break without them. In addition, the [sweet synthesis](https://kol.coldfront.net/thekolwiki/index.php/Sweet_Synthesis) skill is currently required.
