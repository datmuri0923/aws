counter=1
for filename in *file*;
do
file_end=`tail -c 2 $filename`
if [ $file_end == ',' ];
then
truncate -s -2 $filename
mv $filename file_${counter}.txt
counter=$((counter+1))
else
mv $filename file_${counter}.txt
counter=$((counter+1))
fi
done
