#!/bin/bash

# Use bash's random number feature to seed rand.bc's random number
# generator (bc has no means of generating a seed).

# This script can be used instead of the bc executable to start
# bc when random numbers are required.

TEMPFILE=/tmp/$(basename $0).$$.bc
echo "scale=20;rand_seed = $RANDOM.$RANDOM$RANDOM$RANDOM/10" > $TEMPFILE
echo "rand_seed+=20/rand_seed;rand_seed-=13/rand_seed" >> $TEMPFILE

\bc rand.bc $TEMPFILE "$@"
\rm -f $TEMPFILE
