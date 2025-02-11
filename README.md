# mcr
mcr(){ while read -r i; do eval "$( printf "%s" "$i" | awk "$1" ; )" ; done ; } ;
