To run long running processes such as screen or tmux that should survive logout then run them as systemd user services. An advantage of this is this scope already contains an auto renewing Kerberos ticket.

## Using the Provided Systemd User Unit for Tmux or Screen
You need to connect to the same server of lx plus again. 
In an example case run: 
```shell
shh idwoesth@lxplus937@cern.ch
```
- Enter password and 2nd factor
- Run 
```shell
tmux ls 
```
and 
```shell
tmux attach
```
to look at the last tmux session



To start a tmux
   ```shell
   systemctl --user start tmux.service
   ```
To start screen
  ```shell
   systemctl --user start screen.service
  ```
All the following tmux examples apply with screen equivalents.

Then attach in the normal way to tmux.
```shell
   tmux attach
```
This **tmux will be left running if the session is terminated**.

In addition it is possible to automatically start tmux on login if not already running
```shell
systemctl --user enable --now tmux.service
```
this only needs to be done **once ever for all lxplus nodes**.

The status of tmux.service unit can be checked
  ```shell
  systemctl --user status tmux.service
  ```

```shell
● tmux.service - tmux default session (detached)
     Loaded: loaded (/usr/lib/systemd/user/tmux.service; disabled; preset: disabled)
     Active: active (running) since Tue 2025-12-09 08:51:44 CET; 3min 5s ago
       Docs: https://gitlab.cern.ch/lxplus/lxplus-user-units
             man:tmux(1)
    Process: 2342831 ExecStartPre=/usr/bin/loginctl enable-linger (code=exited, status=0/SUCCESS)
    Process: 2342832 ExecStart=/usr/bin/tmux new-session -d -s ${SESSION_NAME} (code=exited, status=0/SUCCESS)
   Main PID: 2342834 (tmux: server)
      Tasks: 4 (limit: 374688)
     Memory: 6.2M (peak: 9.3M)
        CPU: 268ms
     CGroup: /user.slice/user-170861.slice/user@170861.service/app.slice/tmux.service
             ├─2342834 /usr/bin/tmux new-session -d -s lxplus919.cern.ch
             ├─2342835 -bash
             ├─2345707 systemctl --user status tmux.service
             └─2345708 less
```

or stopped 
  ```shell
   systemctl --user stop tmux.service
  ```

[hsf-training](https://hsf-training.github.io/analysis-essentials/shell-extras/persistent-screen.html)
The behavior of screen and tmux on lxplus depends on which version of lxplus you are using. - Lxplus 9 
## lxplus9
If you are on lxplus9, your screen or tmux session will be killed when you log out. To avoid this, you must follow the recipe in [KB0008111](https://cern.service-now.com/service-portal?id=kb_article&n=KB0008111) to initialize the session:
```shell
systemctl --user start tmux.service
tmux a
```
This will auto-renew your kerberos ticket as well, obviating the need to call `kinit` or use keytabs. The recipe for lxplus7 _will not work_.

