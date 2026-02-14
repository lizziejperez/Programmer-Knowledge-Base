# Linux Shell

## Change Directory
```
cd
```

Change current working directory to home directory:
```
cd ~
```

## Listing
List all files in current working directory:
```
ls
```

List all file in the directory:

```
ls [directory path]
```

## Copying
Copy the source fileinto the destination directory:
```
cp [source file path] [destination directory path]
```

Copy the entire source directoryinto the destination directory:
```
cp -R [source directory path] [destination directory path]
```

Copy all the files in the source directoryinto the destination directory:
```
cp * [source directory path] [destination directory path]
```

## Moving / Renaming
Move the file to the directory:
```
mv [file] [directory]
```

Rename the file name to new name:
```
mv [file name] [new name]
```

## Removing
Remove the file:
```
rm [file path]
```

Remove the directory:
```
rm -R [directory path]
```

## Redirecting Output
```
[command] > [output file path]
```
1. Creates an output filewith onlythe command's output
2.  Edits the output fileto have onlythe command's output

## Appending Output
Redirect the command's output to the output file appending it to the existing data on the file:
```
[command] >> [output file path]
```

## Pipe
```
[command 1]| [command 2]
```
Output from command 1 is redirected as input for command 2

## Others
Output the contents of the file sorted in alphabetical order:
```
sort [file path]
```

Open the manual to the command:
```
man [command]
```

Output the lines in the file that match the string:
```
grep [string] [file path]
```

Find the file with the string name within the source path:
```
find [source path] -name [string]
```

Create an alias for the command:
```
alias [alias] [command]
```