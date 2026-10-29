# server-reporter

A small read-only shell script that a server runs once a day to report which packages are installed. It makes no change to the server apart from keeping itself up to date.

Each release holds report.sh, its signature report.sh.sig, and the two public keys current.pem and backup.pem. The script is signed, and an installed copy updates itself only to a release whose signature verifies.

To check a download by hand:

    openssl dgst -sha256 -verify current.pem -signature report.sh.sig report.sh

It must print Verified OK. The release notes give the SHA-256 of report.sh and the fingerprint of each public key.
