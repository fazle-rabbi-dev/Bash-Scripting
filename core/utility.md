<h2 align="center">Bash Utility</h2>

### Execute remote script
```sh
bash <(curl -s https://raw.githubusercontent.com/fh-rabbi/Bash-Utility/main/create-flask-app.sh)
```

### Check packages installed or not
```sh
#!/bin/bash

if command -v python &>/dev/null; then
    echo "Python is installed on Termux."
else
    echo "Python is not installed on Termux."
fi
```

### Check dir exists or not
```sh
# First Method
if [ -d "/path/to/directory" ]; then
    echo "Directory exists"
else
    echo "Directory does not exist"
fi


# Second Method
if test -d "/path/to/directory"; then
    echo "Directory exists"
else
    echo "Directory does not exist"
fi
```

### Check file exist or not
```sh
if [ -f /path/to/file ]; then
    echo "File exists"
else
    echo "File does not exist"
fi
```

### Make get requests
```sh
curl -o output.txt http://example.com/api/resource
```

### Make post requests
```sh
curl --location --request POST 'https://example.com/api/login' \
--header 'Content-Type: application/json' \
--data-raw '{
    "email": "user@example.com",
    "password": "mypassword"
}'
```

### Download a file
```sh
function download_file {
    url="$1"
    filename="$2"
    curl -L -o "$filename" "$url"
}
```

### Make zip file
```sh
# The name of the zip file you want to create
zip_file="example.zip"

# The directory you want to include in the zip file
source_dir="/path/to/source/dir"

# Create the zip file
zip -r $zip_file $source_dir
```

### Unzip
```sh
# The name of the zip file you want to extract
zip_file="example.zip"

# The directory where you want to extract the files
extract_dir="/path/to/extract/dir"

# Extract the zip file
unzip $zip_file -d $extract_dir
```

### Check internet
```sh
check_internet() {
  if ping -q -c 1 -W 1 google.com > /dev/null 2>&1; then
    echo "Internet connection is OK"
    check_internet
  else
    echo "Internet connection is not OK"
  fi
}
```

### Check file exists or not in remote
```sh
check_url() {
  if wget --spider "$1" 2>/dev/null; then
    echo "URL exists"
  else
    echo "URL does not exist"
  fi
}

check_url "https://raw.githubusercontent.com/noob-hackers/patchupdateznh/main/spmx.v.1"
```

### While doing some task print animation
```sh
while git clone https://github.com/fh-rabbi/Bash-Utility 2> /dev/null; do 
    printf  "\e[92m▓▓▓▓▓▓▓▓▓▓▓▓▓\e[0m"
    sleep 1
done
```

