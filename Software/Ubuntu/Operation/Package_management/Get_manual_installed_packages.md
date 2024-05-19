# Get manual installed packages
Created Sonntag 24 März 2024

List all manual installed packages:
# comm -23 <(apt-mark showmanual | sort -u) <(gzip -dc /var/log/installer/initial-status.gz | sed -n 's/^Package: //p' | sort -u)

