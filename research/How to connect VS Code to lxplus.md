The issue with **VS Code Remote SSH** and CERN’s **lxplus** is that lxplus is a cluster of machines, so a standard hostname like `lxplus.cern.ch` can point to any machine. VS Code Remote SSH needs a consistent target IP or hostname to establish a reliable connection.

To connect VS Code to lxplus 

- Make sure that the extension **Remote - SHH** is installed
- Klick *open an remote window* (><) lower left corner
- Klick *Connect to Host*
- Klick *Configure SSH Hosts*
- Klick the config file `/Users/<username>/.ssh/config`
- Add to file
```shell
Host lxplus.cern.ch
	HostName lxplus.cern.ch
	User <cern user name>
```

1. Go to VS Code settings
	**Linux/Windows**: Click on the top menu bar → **File** → **Preferences** → **Settings** 
	or use shortcut `Ctrl + ,`
	**Mac**: Click on the top menu bar → **Code** → **Preferences** → **Settings** 
	or use shortcut `Cmd + ,`
2. Search settings for `conda server` - or `Remote.SSH: Server Install Path`
	find: 
	
	**Remote.SSH: Server Install Path** *(Applies to all profiles)*
	A map of remote host to absolute path where the VS Code server will be installed. By default the server is installed in the home directory of every remote. **Note**: By changing this setting you may need to clean up other installations of `.vscode-server` on your remote that isn't in the path you've configured.
	
1. Set
	**Item** to `lxplus.cern.ch` and 
	**Value** to `/eos/user/<first_letter_of_your_cern_username>/<your_cern_username>/`

**If you are at CERN do the same just with lxplus and not lxplus.cern.ch everywhere**
