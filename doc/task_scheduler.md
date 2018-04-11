# Start Miner at PC Login - Automation Tool

## 1. Create a Scheduled task to start the miner at login
	1. Windows Start button: Type: "Task Scheduler"
	2. Select "Action" tab:
		1. "Create Task"
	3. On the "General" tab:
		1. Enter a name: "Start Miner"  (or name of your choice)
		2. Select check box, "Run with highest privileges"
##	2. On the "Triggers" tab:
		1. Select "New"
		2. In the "Begin the task:" drop-down, select, "At log on"
		3. If it takes your network a while to restart after a power outage, you may want to enter a value in the "Delay task for" field.
		4. Select "OK"
##	3. On the "Actions" tab:
		1. Select "New"
		2. "Action" will already be set to, "Start a program"
		3. Select "Browse" and select your "PreciousGuardian.exe" file
		4. **The "Start in (optional):" field is not optional.  You need to enter the path to the directory that contains PreciousGuardian.exe**
##	4. On the "Conditions" tab:
		1. At the bottom, toggle the option to, "Start only if the following network connection is available" --> "Any connection"
##	5. (Optional) While in Task Scheduler, you may want to select "Task Scheduler Library" in the left hand column and ensure you understand and approve of all the scheduled tasks.  Make sure they are appropriate for your rig.