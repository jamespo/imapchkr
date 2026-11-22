# imapchkr
Command-line IMAP mail checker for Python 3 with output options for xbar & waybar.

[Check the wiki!](https://github.com/jamespo/imapchkr/wiki)

## Config

Create ~/.config/.imapchkr.conf with 1 or more sections as below:

    [mailservername]
    user=james
    password=2347923rbkaa
    server=yourimapserver.com
    newmail_cmd=/usr/bin/ogg123 /usr/share/sounds/gnome/default/alerts/sonar.ogg   # optional
    folders=INBOX,Work   # optional, defaults to INBOX

### cipherstore credentials (optional)

`user` and/or `password` can be fetched from [cipherstore](https://github.com/jamespo/cipherstore)
instead of being stored in plain text. Prefix the value with `cipherstore:` followed by the token id:

    user=cipherstore:imap-myacct-user
    password=cipherstore:imap-myacct-pass

This needs the cipherstore Python client (`contrib/python/cipherstore.py`) on `PYTHONPATH`
and the store unlocked. If a token can't be retrieved imapchkr exits with an error.
Plain-text credentials keep working without the module installed.

### Environment Vars

Set IMAPCTM to customize IMAP connnection timeout (int in seconds)

## Usage

    Usage: imapchkr [options]

    Options:
      -h, --help    show this help message and exit
      -c CONFFILE   config file
      -b            b/w output
      -s            short output
      -l            list mail summary
      -w, --waybar  waybar output
      -f FOLDERS    folders to check (acct:f1,f2;acct2:f3,f4)
      -n NRECENT    show n most recent emails (unread or not)
      -p PIDPATH    pid path

## Notes

Only supports IMAPS (port 993).
