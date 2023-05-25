# shell-script

#Create a shell script to print the HTTP error code of guvi.in & print, the success/failure message based on the error code response
#!/bin/bash

url="http://guvi.in"
http_code=$(curl -s -o /dev/null -w "%{http_code}" $url)

if [[ $http_code -eq 200 ]]; then
  echo "Success! HTTP code: $http_code"
else
  echo "Failure! HTTP code: $http_code"
fi

#Given a file, replace all occurrence of the word ""give"" with ""learning"" from 5th line till the end in only those lines that contain the word "welcome"

#!/bin/bash

filename="example.txt"

sed '5,$ {/welcome/s/give/learning/g}' "$filename" > temp.txt
mv temp.txt "$filename"

