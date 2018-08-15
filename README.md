# masternode-miner

THIS SOFTWARE IS NOW OBSOLETE!
Should no longer be used. For a masternode guide, follow: https://forum.arionum.com/viewtopic.php?f=13&t=367&p=1669#p1669


A proof of concept masternode miner for Arionum.

## REQUIREMENTS

1. 8 GB RAM
2. 100GB+ DISK SPACE (SSD)
3. 4 CPU Cores
4. 100.000 ARO

## IMPORTANT INFORMATION

The masternodes are implemented starting block 80.000

The cost of a masternode is 100.000 ARO

The masternode will win one of every 3 blocks.

You should create a new wallet for the masternode. Do not use this wallet for anything else.

The rewards are available immediately after a block has been won.

The funds are locked for a minimum of 3 Months.

In order to release the funds, the miner must be paused for 1 month (no won blocks) before a release is accepted. This means that if you want to close the masternode after 3 months, you must pause the masternode after 60 days.

The block winners are chosen in order, so everyone will get their blocks. There's no chance involved.

You must be sure that the IP you set for the masternode will be yours until you decide to close the masternode. 

The masternode must have 99+% uptime

**Keep in mind this is only the very first version of masternodes, which deals mostly with mining. A lot of functionality will be added in the near future and it will be very important to keep your node updated and with the required resources.**

## INSTALL INSTRUCTIONS

1. Create a new wallet using the [CLI Wallet](https://github.com/arionum/lightWalletCLI)
2. Send 100.010 ARO to the new address.
3. Install the Arionum node on the same server. The node must be accessible on ip + port 80, ex: http://1.1.2.2
4. Edit the `config.inc.php`, set `$_config['masternode']` to `true` and the 
`$_config['masternode_public_key']` to the wallet's public key.
5. Download the [masternode-miner](https://github.com/arionum/masternode-miner) to a secure location 
on the same server.
6. Create a .env file in the same folder as the masternode-miner and add in it the public key on the first row and the private key on the second row.
7. Make the miner executable using `chmod +x masternode-miner`
8. Create a cronjob to run every minute the masternode-miner file.
9. Using the cli wallet, run the command: `./light-arionum-cli masternode create [ip]` (replace the IP 
with the actual IP)
10. Wait 360 blocks and your masternode will start mining.

### Example cron job

```
* * * * * YOURUSER /home/YOURUSER/masternode-miner/masternode-miner >/dev/null
```

### Example .env:

*For extra security, you can keep your masternode miner and your keys on a separate secure server by
adding the masternode address on the third row of the `.env` file as shown in the example.*

```
public-key
private-key
http://10.0.1.1
```
