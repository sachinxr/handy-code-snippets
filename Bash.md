```
mv *string* directory/
```

Replace string 'foo' with 'bar' throughout the file

```
sed 's/foo/bar/g' file
```

Search for rows with either string 'foo' or 'bar' in a file
```
grep 'foo\|bar' file
```

Keep rows that start with a particular phrase

```
grep ^phrase.* file
```

Keep rows if word matches any of the values in another file of IDs

```
grep -Fwf id.file file
```

Compare column #m in file 1 and column #2 in file 2 and keep all rows of file 2 where the two values match

```
awk 'FNR==NR{a[$m]; next} ($n) in a{print}' file1 file2
    
# Compare multiple columns, but keep few columns
awk 'FNR==NR{a[$m, $n, $o]; next} ($x, $y, $z) in a{print $x'\t'$y}' file1 file2
```

Swap columns #1 and #2 in a file

```
awk '{t = $1; $1 = $2; $2 = t; print;}' file
```

Extract files from a .bz2 archive

```
bzip2 -d file.bz2
    
# To keep the zipped file
bzip2 -dk file.bz2
```

Count unique values in a column #2

```
cut -f2 filename | sort | uniq | wc -l
    
# Or
cut -f2 filename | sort -u | wc -l
```


