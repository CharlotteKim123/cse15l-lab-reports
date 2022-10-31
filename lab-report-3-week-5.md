# **Lab Report 3: Grep**

## **Option #1: -l**

**Example #1**

```
# code block

charlottekim@Charlottes-MacBook-Air 911report % grep -l "chapter" *.txt 
chapter-1.txt
chapter-10.txt
chapter-11.txt
chapter-12.txt
chapter-13.1.txt
chapter-13.3.txt
chapter-13.4.txt
chapter-13.5.txt
chapter-2.txt
chapter-3.txt
chapter-5.txt
chapter-6.txt
chapter-7.txt
chapter-8.txt
chapter-9.txt

```
grep -l "chapter" *.txt returns the files that contains the word "chapter". This is helpful because instead of looking through each file to find which files have a word you're looking for, you can just type grep -l "chapter" *.txt. 

**Example #2**

```
# code block

charlottekim@Charlottes-MacBook-Air 911report % grep -l "chapter" chapter-3.txt
chapter-3.txt

```

I used grep -l "chapter" chapter-3.txt to check if "chapter" was in that file. This is helpful for you to check if a certain file has the word or phrase you're looking for.

**Example #3**

```
# code block

charlottekim@Charlottes-MacBook-Air docsearch % grep -1 "mortality" technical/biomed/1468-6708-3-1.txt 
        even though there is little evidence that overweight is
        associated with increased mortality in those over age 65.
        Six large controlled population-based studies of
        non-smoking older adults have investigated the association
        between body mass index (BMI) and mortality, controlling
        for relevant covariates [ 1 2 3 4 5 6 ] . All studies found
--
        In older adults, risk factors may have a greater effect
        on health than on mortality. If so, then behavior change
        trials of weight modification might be more successful if
        they were evaluated on improved health, rather than on
        decreased mortality. Clinical trials powered to detect
        differences in YHL would often require fewer subjects than
--
          baseline covariates that were prevalent in the elderly,
          related to mortality and morbidity in previous studies,
          and likely to be related to BMI. Self-reported covariates
--
          requires specific attention to improved health and
          mortality.
          Interestingly, the strongest health relationships were
--
        Recommendations for desirable weight have been
        criticized for emphasizing mortality rather than health. We
        found associations between YHL and obesity that were not
        present in the mortality analysis, suggesting that YHL may
        be a more sensitive measure of the burden of obesity in

```

grep -1 "mortality" technical/biomed/1468-6708-3-1.txt returns the paragraphs that contains the word "mortality" in the file 1468-6708-3-1.txt. This is useful to find certain paragraphs that contain the info you need.

## **Option #2: -o**

**Example #1**

```
# code block

charlottekim@Charlottes-MacBook-Air docsearch % grep -o "mortality" technical/biomed/1468-6708-3-1.txt 
mortality
mortality
mortality
mortality
mortality
mortality
mortality
mortality

```

grep -o "mortality" technical/biomed/1468-6708-3-1.txt returns every instance the word "mortality" shows up in the file 1468-6708-3-1.txt. This is helpful if you need to find how many instances of a word there are in a file.
 
**Example #2**

```
# code block

charlottekim@Charlottes-MacBook-Air 911report % grep -o "help" *.txt
chapter-1.txt:help
chapter-1.txt:help
chapter-1.txt:help
chapter-1.txt:help
chapter-1.txt:help
chapter-1.txt:help
chapter-1.txt:help
chapter-10.txt:help
chapter-10.txt:help
chapter-10.txt:help
chapter-10.txt:help
chapter-10.txt:help
chapter-11.txt:help
chapter-11.txt:help
...
```

grep -o "help" *.txt returns every instance the word "mortality" shows up in the files that end in ".txt". This is helpful if you need to find how many instances of a word there are in all the files.

**Example #3**

```
# code block

charlottekim@Charlottes-MacBook-Air biomed % grep -o "2003" *.txt
1471-2105-4-25.txt:2003
1471-2105-4-25.txt:2003
1471-2164-4-26.txt:2003
1471-2164-4-26.txt:2003
1471-2164-4-26.txt:2003
1471-2164-4-26.txt:2003
1471-2407-3-16.txt:2003
1471-2458-3-20.txt:2003
1471-2458-3-20.txt:2003
1471-2458-3-20.txt:2003
1472-6882-3-3.txt:2003
1472-6882-3-3.txt:2003
1472-6947-3-5.txt:2003
1472-6947-3-5.txt:2003
1472-6947-3-8.txt:2003
1472-6963-3-13.txt:2003
bcr602.txt:2003
gb-2001-2-7-research0025.txt:2003
gb-2003-4-4-r28.txt:2003

```

grep -o "2003" *.txt returns the files that have "2003" in their names. This is helpful is you need to find a certain set of files or a certain file.

## **Option #3: -n**

**Example #1**

```
# code block 

charlottekim@Charlottes-MacBook-Air biomed % grep -n "genomic" gb-2003-4-9-r60.txt
6:        The post-genomic era has introduced high-throughput

```

grep -n "genomic" gb-2003-4-9-r60.txt returns the line number that contains the word "genomic". This is helpful if you need to find where a certain word or phrase is.

**Example #2**

```
# code block 

charlottekim@Charlottes-MacBook-Air biomed % grep -n "genomic" *.txt

1471-2164-2-9.txt:295:          of the genomic organization of the corresponding genes
1471-2164-2-9.txt:298:          with the corresponding genomic sequences available in
1471-2164-2-9.txt:299:          genomic databases (Table 1). For all families, the
1471-2164-2-9.txt:300:          genomic organization of several members of the family
1471-2164-2-9.txt:472:          proteins. Likewise, analysis of their genomic
1471-2164-2-9.txt:656:          genomic clone) which contains almost all and displays
1471-2164-3-1.txt:51:          recent analysis of their genomic sequences [ 21 ] . The
1471-2164-3-1.txt:94:          genomic DNA had been the template, products greater than
1471-2164-3-10.txt:187:        Extensive analysis of the genomic organization of the MHC
1471-2164-3-10.txt:202:        map study and attempts to study the genomic proximity of
1471-2164-3-10.txt:258:          human genomic sequence based on the Washington
1471-2164-3-10.txt:272:          genomic counterpart over half the length of ESTs' length
1471-2164-3-13.txt:63:        individuals [ 8 ] . The gene spans 350 kb of genomic DNA
1471-2164-3-13.txt:402:          NF1 genomic sequence (Genbank
...
```

grep -n "genomic" *.txt returns the line numbers in each file that contains the word "genomic." This is helpful if you need to use certain files that has the topic or word that you need.

**Example #3**

```
# code block 

charlottekim@Charlottes-MacBook-Air biomed % grep -n "." gb-2003-4-9-r60.txt
2:  
3:    
4:      
5:        Rationale
6:        The post-genomic era has introduced high-throughput
7:        methodologies that generate experimental data at rates that
8:        exceed knowledge growth. In particular, high-density
9:        biochips including complementary deoxyribonucleic acid
10:        (cDNA) microarrays, oligonucleotide microarrays, and
11:        rapidly evolving proteomics platforms represent modern
12:        tools able to interrogate biology on a genome-wide scale
13:        and generate tens of thousands of data points
14:        simultaneously [ 1 ] . While researchers are beginning to
...
```

grep -n "." gb-2003-4-9-r60.txt returns the line numbers in each file that contains a period. This is helpful if you need a complicated way to find how many sentences a file has.