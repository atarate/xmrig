# XMRig
XMRig is high performance Monero (XMR) CPU miner, with the official full Windows support.
Originally based on cpuminer-multi with heavy optimizations/rewrites and removing a lot of legacy code, since version 1.0.0 complete rewritten from scratch on C++.

* This is the ARMv8 CPU-mining version under development - do not use

### Options
```
  -a, --algo=ALGO       cryptonight (default) or cryptonight-lite
  -o, --url=URL         URL of mining server
  -O, --userpass=U:P    username:password pair for mining server
  -u, --user=USERNAME   username for mining server
  -p, --pass=PASSWORD   password for mining server
  -t, --threads=N       number of miner threads
  -v, --av=N            algorithm variation, 0 auto select
  -k, --keepalive       send keepalived for prevent timeout (need pool support)
  -r, --retries=N       number of times to retry before switch to backup server (default: 5)
  -R, --retry-pause=N   time to pause between retries (default: 5)
      --cpu-affinity    set process affinity to CPU core(s), mask 0x3 for cores 0 and 1
      --cpu-priority    set process priority (0 idle, 2 normal to 5 highest)
      --no-huge-pages   disable huge pages support
      --no-color        disable colored output
      --donate-level=N  donate level, default 5% (5 minutes in 100 minutes)
      --user-agent      set custom user-agent string for pool
  -B, --background      run the miner in the background
  -c, --config=FILE     load a JSON-format configuration file
  -l, --log-file=FILE   log all output to a file
      --max-cpu-usage=N maximum CPU usage for automatic threads mode (default 75)
      --safe            safe adjust threads and av settings for current CPU
      --nicehash        enable nicehash support
      --print-time=N    print hashrate report every N seconds
  -h, --help            display this help and exit
  -V, --version         output version information and exit
```

Also you can use configuration via config file, default **config.json**. You can load multiple config files and combine it with command line options.

## Algorithm variations
Since version 0.8.0.
* `--av=1` For CPUs with hardware AES.
* `--av=2` Lower power mode (double hash) of `1`.
* `--av=3` Software AES implementation.
* `--av=4` Lower power mode (double hash) of `3`.

## Common Issues
### HUGE PAGES unavailable
* Run XMRig as Administrator.
* Since version 0.8.0 XMRig automatically enable SeLockMemoryPrivilege for current user, but reboot or sign out still required. [Manual instruction](https://msdn.microsoft.com/en-gb/library/ms190730.aspx).

## Other information
* No HTTP support, only stratum protocol support.
* No TLS support.
* Default donation 5% (5 minutes in 100 minutes) can be reduced to 1% via command line option `--donate-level`.


### CPU mining performance
Under Development
