#!/bin/bash

#Q1 - Write an awk command to extract only ERROR messages along with their timestamps.
awk '$2 == "ERROR" { print $1, $4 }' logfile.txt

#Q2 - Given a csv file to write an awk script to compute the average of each subject.
awk 'NR>1 {math+=$2; sci+=$3; eng+=$4; count++} END { print "Math:", math/count; print "Science:", sci/count;
print "English:", eng/count }' FS='\t' marks.csv

#Q3 - To write an awk script to count occurances of each IP.
awk '{ count[$1]++ } END { for (ip in count) print ip, count[ip] }' server.log

#Q4 - Write a sed command to swap the first and last words.
sed 's/^\([^ ]*\)\(.*\) \([^ }*\)$/\3\2 \1/' fruit.txt


#Q5 - To write a sed command to remove consecutive duplicate words.
cat duplicate.txt
sed 's/\b\([[:alnum:]]\+\) \1\b/\1/g' duplicate.txt
