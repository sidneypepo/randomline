# randomline
Just an example of choose a random line in text file, coded in Shell Script.

---

# How this example code works? See it below.

## Importing file
> You can change the variable name that I called '$file' and replace 'list.txt' by the path and name of the file that you want use
```bash
file=list.txt
```

## Choosing random line
> You can change the variable name that I called '$line', remembering to change the variable '$file' name, if you have changed it in previous step
```bash
line=$((1 + RANDOM % $(cat $file | wc -l)))
```

## Reading the word that is in the choosed line
> You can change the variable name that I called '$word', remembering to change the variables '$file' and '$line' names, if you have changed them in previous steps
```bash
word=$(cat $file | tr "\n" ":" | cut -d ":" -f "$line")
```

## Printing the random line and the respective word
> If you changed the variables names '$line' and '$word', change them below too
```bash
echo -e "The random line choosed is: $line\nThe word that is in that line is: $word\n"
```
