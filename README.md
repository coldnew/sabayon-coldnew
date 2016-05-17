# sabayon-coldnew
coldnew's Sabayon Linux repository

# Add this repo to your sabayon

To use this binary host, you can use follwoing command to add it to you Sabayon Linux system:

```sh
equo repo add coldnew \
     --desc "coldnew's Sabayon Linux Repository" \
     --repo https://coldnew.github.io/sabayon-coldnew//#bz2  \
     --pkg https://coldnew.github.io/sabayon-coldnew/
```

then update the entropy info

```sh
equo update
```

# How to create repo like this ?

Here are some info how I create this repo

## Use portage build package 

emerge -avB slic3r-bin

## Translate it to entropy package

mkdir -p /tmp/packages
equo pkg inflate --savedir  /tmp/packages /usr/portage/packages/media-gfx/slic3r-bin-1.2.9.tbz2

## add it

eit inject -h  /tmp/packages/media-gfx/media-gfx\:slic3r-bin-1.2.9.ab435eab728789df8d0ea4e5aafe43c21f7adcf6~9999.tbz2

## push it

eit push

