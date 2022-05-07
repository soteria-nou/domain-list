# Soteria nou's domain list (cleaned)

This repository contains lists of domains from `master` branch except those inside `excluded.txt` file that were reported by the users as they are needed to keep websites working.

### Usage
Each list or a concatenated list must be additionally adapted to be used as hosts file or by dnsmasq, bind or any other dns server software or web filtering solution.

### License
You are free to copy and distribute any of these lists for non-commercial uses as long the original URL is included.

#### Script
These files were created by the following script.
```
find . -maxdepth 1 -type f -name \*.txt \! -name excluded.txt | while read f; do
  grep -Fvx -f excluded.txt "$f" >tmp.txt
  mv tmp.txt "$f"
done
```