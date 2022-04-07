##my bashscript for get csv and show in mysql


*#!/bin/bash

*# Purpose: Read Comma Separated CSV File

*# Author: Vivek Gite under GPL v2.0+

*# ------------------------------------------

INPUT=testingzahra.csv

OLDIFS=$IFS

IFS=','

[ ! -f $INPUT ] && { echo "$INPUT file not found"; exit 99; }

while read DATE sender firewallAction count 

do
        echo "date : $DATE"
        echo "sender : $sender"
        echo "sample : $firewallAction"
        echo "count : $count"





mysql test << EOF


INSERT INTO test (\`DATE\`, \`sender\`, \`firewallAction\`, \`count\`) VALUES ("$DATE", "$sender", "$firewallAction", "$count");
EOF

done < $INPUT
IFS=$OLDIFS
~                                      