1. The conclusions of the trial are different because of one critical difference— the uncertainty of the sex/height. While the medical example has a situation where the sex is readily available data, the farmer does not know about what the plant's height will be. The judgement of exchangeability changes and this is why the conclusions are different.
2. Let V = Variety, Y = Yield, and H = Height

![12-10-23, 3:37 PM Microsoft Lens](https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/cfbe1212-3c0d-4ea3-9628-c2e9686a93af)


The Variety here affects both Height and Yield, but the textbook also mentions "...it is perhaps because of this tendency of the black variety TO GROW TALL that is provides a HIGHER YIELD", so I see that Height affects Yield as well.
4. 
```
# set trial participants and number of them that will have diabetes
n_total <- 100
n_diabetes <- 25

diabetes_status <- rep(c("Diabetes", "No diabetes"), c(n_diabetes, n_total - n_diabetes))

# assign them with treatments
treatment <- rep(c("Treatment A", "Treatment B"), each = n_total, length = 100)

# randomize order
randomized_order <- sample(1:n_total)

# sort by diabetes order
randomized_table <- data.frame(diabetes_status, treatment, randomized_order)
randomized_table <- randomized_table[order(randomized_table$diabetes_status, randomized_table$randomized_order),]

# print
print(randomized_table)
```

For which I got this table:

```
diabetes_status   treatment randomized_order
21         Diabetes Treatment A                1
1          Diabetes Treatment A                3
20         Diabetes Treatment A                4
8          Diabetes Treatment A               20
3          Diabetes Treatment A               23
12         Diabetes Treatment A               24
15         Diabetes Treatment A               25
18         Diabetes Treatment A               40
19         Diabetes Treatment A               43
6          Diabetes Treatment A               46
13         Diabetes Treatment A               47
5          Diabetes Treatment A               54
10         Diabetes Treatment A               57
4          Diabetes Treatment A               59
22         Diabetes Treatment A               62
2          Diabetes Treatment A               63
17         Diabetes Treatment A               64
7          Diabetes Treatment A               71
9          Diabetes Treatment A               81
11         Diabetes Treatment A               83
24         Diabetes Treatment A               87
25         Diabetes Treatment A               92
16         Diabetes Treatment A               96
14         Diabetes Treatment A               98
23         Diabetes Treatment A              100
45      No diabetes Treatment A                2
53      No diabetes Treatment A                5
94      No diabetes Treatment A                6
93      No diabetes Treatment A                7
79      No diabetes Treatment A                8
29      No diabetes Treatment A                9
46      No diabetes Treatment A               10
48      No diabetes Treatment A               11
44      No diabetes Treatment A               12
86      No diabetes Treatment A               13
43      No diabetes Treatment A               14
65      No diabetes Treatment A               15
84      No diabetes Treatment A               16
27      No diabetes Treatment A               17
38      No diabetes Treatment A               18
39      No diabetes Treatment A               19
40      No diabetes Treatment A               21
67      No diabetes Treatment A               22
36      No diabetes Treatment A               26
89      No diabetes Treatment A               27
57      No diabetes Treatment A               28
58      No diabetes Treatment A               29
68      No diabetes Treatment A               30
30      No diabetes Treatment A               31
64      No diabetes Treatment A               32
66      No diabetes Treatment A               33
72      No diabetes Treatment A               34
47      No diabetes Treatment A               35
74      No diabetes Treatment A               36
88      No diabetes Treatment A               37
54      No diabetes Treatment A               38
52      No diabetes Treatment A               39
71      No diabetes Treatment A               41
82      No diabetes Treatment A               42
73      No diabetes Treatment A               44
37      No diabetes Treatment A               45
41      No diabetes Treatment A               48
59      No diabetes Treatment A               49
100     No diabetes Treatment A               50
49      No diabetes Treatment A               51
33      No diabetes Treatment A               52
60      No diabetes Treatment A               53
69      No diabetes Treatment A               55
98      No diabetes Treatment A               56
85      No diabetes Treatment A               58
50      No diabetes Treatment A               60
63      No diabetes Treatment A               61
42      No diabetes Treatment A               65
61      No diabetes Treatment A               66
95      No diabetes Treatment A               67
70      No diabetes Treatment A               68
87      No diabetes Treatment A               69
51      No diabetes Treatment A               70
31      No diabetes Treatment A               72
77      No diabetes Treatment A               73
83      No diabetes Treatment A               74
76      No diabetes Treatment A               75
28      No diabetes Treatment A               76
99      No diabetes Treatment A               77
34      No diabetes Treatment A               78
62      No diabetes Treatment A               79
55      No diabetes Treatment A               80
90      No diabetes Treatment A               82
75      No diabetes Treatment A               84
92      No diabetes Treatment A               85
56      No diabetes Treatment A               86
91      No diabetes Treatment A               88
80      No diabetes Treatment A               89
26      No diabetes Treatment A               90
97      No diabetes Treatment A               91
81      No diabetes Treatment A               93
32      No diabetes Treatment A               94
35      No diabetes Treatment A               95
78      No diabetes Treatment A               97
96      No diabetes Treatment A               99
153     No diabetes Treatment B              100
```
