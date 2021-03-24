# imapchkr
Command-line IMAP mail checker for Python 3

[Check the wiki!](https://github.com/jamespo/imapchkr/wiki)

## Config

Create ~/.config/.imapchkr.conf with 1 or more sections as below:

    [mailservername]
    user=james
    password=2347923rbkaa
    server=yourimapserver.com
    newmail_cmd=/usr/bin/ogg123 /usr/share/sounds/gnome/default/alerts/sonar.ogg   # optional
    folders=INBOX,Work   # optional, defaults to INBOX
    
## Usage

    Usage: imapchkr [options]

    Options:
      -h, --help  show this help message and exit
      -b          b/w output
      -s          short output
      -l          list mail summary

## Notes

Only supports IMAPS (port 993).
