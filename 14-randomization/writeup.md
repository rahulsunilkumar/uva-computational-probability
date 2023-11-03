1. The conclusions of the trial are different because of one critical difference— the uncertainty of the sex/height. While the medical example has a situation where the sex is readily available data, the farmer does not know about what the plant's height will be. The judgement of exchangeability changes and this is why the conclusions are different.
2. Let V = Variety, Y = Yield, and H = Height

<img width="279" alt="Screenshot 2023-11-03 at 6 38 05 AM" src="https://github.com/rahulsunilkumar/ds2006-sunilkumar-rahul/assets/143004275/b7118b3a-695f-4f01-b743-27e53dffe507">

4. 
```
# set trial participants and number of them that will have diabetes
n_total <- 100
n_diabetes <- 25

diabetes_status <- rep(c("Diabetes", "No diabetes"), c(n_diabetes, n_total - n_diabetes))

# assign them with treatments
treatment <- rep(c("Treatment A", "Treatment B"), each = n_total)

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
16         Diabetes Treatment A                2
116        Diabetes Treatment B                2
12         Diabetes Treatment A                6
112        Diabetes Treatment B                6
22         Diabetes Treatment A               10
122        Diabetes Treatment B               10
5          Diabetes Treatment A               21
105        Diabetes Treatment B               21
24         Diabetes Treatment A               23
124        Diabetes Treatment B               23
3          Diabetes Treatment A               26
103        Diabetes Treatment B               26
1          Diabetes Treatment A               28
101        Diabetes Treatment B               28
13         Diabetes Treatment A               30
113        Diabetes Treatment B               30
15         Diabetes Treatment A               31
115        Diabetes Treatment B               31
21         Diabetes Treatment A               40
121        Diabetes Treatment B               40
20         Diabetes Treatment A               42
120        Diabetes Treatment B               42
18         Diabetes Treatment A               54
118        Diabetes Treatment B               54
7          Diabetes Treatment A               62
107        Diabetes Treatment B               62
8          Diabetes Treatment A               63
108        Diabetes Treatment B               63
6          Diabetes Treatment A               65
106        Diabetes Treatment B               65
17         Diabetes Treatment A               69
117        Diabetes Treatment B               69
23         Diabetes Treatment A               71
123        Diabetes Treatment B               71
14         Diabetes Treatment A               72
114        Diabetes Treatment B               72
25         Diabetes Treatment A               75
125        Diabetes Treatment B               75
4          Diabetes Treatment A               77
104        Diabetes Treatment B               77
11         Diabetes Treatment A               82
111        Diabetes Treatment B               82
9          Diabetes Treatment A               85
109        Diabetes Treatment B               85
19         Diabetes Treatment A               93
119        Diabetes Treatment B               93
10         Diabetes Treatment A               94
110        Diabetes Treatment B               94
2          Diabetes Treatment A               98
102        Diabetes Treatment B               98
72      No diabetes Treatment A                1
172     No diabetes Treatment B                1
76      No diabetes Treatment A                3
176     No diabetes Treatment B                3
49      No diabetes Treatment A                4
149     No diabetes Treatment B                4
34      No diabetes Treatment A                5
134     No diabetes Treatment B                5
42      No diabetes Treatment A                7
142     No diabetes Treatment B                7
73      No diabetes Treatment A                8
173     No diabetes Treatment B                8
81      No diabetes Treatment A                9
181     No diabetes Treatment B                9
47      No diabetes Treatment A               11
147     No diabetes Treatment B               11
88      No diabetes Treatment A               12
188     No diabetes Treatment B               12
87      No diabetes Treatment A               13
187     No diabetes Treatment B               13
91      No diabetes Treatment A               14
191     No diabetes Treatment B               14
32      No diabetes Treatment A               15
132     No diabetes Treatment B               15
89      No diabetes Treatment A               16
189     No diabetes Treatment B               16
31      No diabetes Treatment A               17
131     No diabetes Treatment B               17
67      No diabetes Treatment A               18
167     No diabetes Treatment B               18
40      No diabetes Treatment A               19
140     No diabetes Treatment B               19
58      No diabetes Treatment A               20
158     No diabetes Treatment B               20
70      No diabetes Treatment A               22
170     No diabetes Treatment B               22
77      No diabetes Treatment A               24
177     No diabetes Treatment B               24
100     No diabetes Treatment A               25
200     No diabetes Treatment B               25
75      No diabetes Treatment A               27
175     No diabetes Treatment B               27
90      No diabetes Treatment A               29
190     No diabetes Treatment B               29
39      No diabetes Treatment A               32
139     No diabetes Treatment B               32
52      No diabetes Treatment A               33
152     No diabetes Treatment B               33
43      No diabetes Treatment A               34
143     No diabetes Treatment B               34
80      No diabetes Treatment A               35
180     No diabetes Treatment B               35
74      No diabetes Treatment A               36
174     No diabetes Treatment B               36
56      No diabetes Treatment A               37
156     No diabetes Treatment B               37
65      No diabetes Treatment A               38
165     No diabetes Treatment B               38
61      No diabetes Treatment A               39
161     No diabetes Treatment B               39
71      No diabetes Treatment A               41
171     No diabetes Treatment B               41
78      No diabetes Treatment A               43
178     No diabetes Treatment B               43
95      No diabetes Treatment A               44
195     No diabetes Treatment B               44
69      No diabetes Treatment A               45
169     No diabetes Treatment B               45
29      No diabetes Treatment A               46
129     No diabetes Treatment B               46
55      No diabetes Treatment A               47
155     No diabetes Treatment B               47
41      No diabetes Treatment A               48
141     No diabetes Treatment B               48
97      No diabetes Treatment A               49
197     No diabetes Treatment B               49
63      No diabetes Treatment A               50
163     No diabetes Treatment B               50
84      No diabetes Treatment A               51
184     No diabetes Treatment B               51
38      No diabetes Treatment A               52
138     No diabetes Treatment B               52
36      No diabetes Treatment A               53
136     No diabetes Treatment B               53
48      No diabetes Treatment A               55
148     No diabetes Treatment B               55
92      No diabetes Treatment A               56
192     No diabetes Treatment B               56
99      No diabetes Treatment A               57
199     No diabetes Treatment B               57
79      No diabetes Treatment A               58
179     No diabetes Treatment B               58
83      No diabetes Treatment A               59
183     No diabetes Treatment B               59
46      No diabetes Treatment A               60
146     No diabetes Treatment B               60
26      No diabetes Treatment A               61
126     No diabetes Treatment B               61
35      No diabetes Treatment A               64
135     No diabetes Treatment B               64
59      No diabetes Treatment A               66
159     No diabetes Treatment B               66
93      No diabetes Treatment A               67
193     No diabetes Treatment B               67
28      No diabetes Treatment A               68
128     No diabetes Treatment B               68
30      No diabetes Treatment A               70
130     No diabetes Treatment B               70
82      No diabetes Treatment A               73
182     No diabetes Treatment B               73
45      No diabetes Treatment A               74
145     No diabetes Treatment B               74
50      No diabetes Treatment A               76
150     No diabetes Treatment B               76
57      No diabetes Treatment A               78
157     No diabetes Treatment B               78
33      No diabetes Treatment A               79
133     No diabetes Treatment B               79
54      No diabetes Treatment A               80
154     No diabetes Treatment B               80
60      No diabetes Treatment A               81
160     No diabetes Treatment B               81
68      No diabetes Treatment A               83
168     No diabetes Treatment B               83
62      No diabetes Treatment A               84
162     No diabetes Treatment B               84
94      No diabetes Treatment A               86
194     No diabetes Treatment B               86
85      No diabetes Treatment A               87
185     No diabetes Treatment B               87
64      No diabetes Treatment A               88
164     No diabetes Treatment B               88
96      No diabetes Treatment A               89
196     No diabetes Treatment B               89
37      No diabetes Treatment A               90
137     No diabetes Treatment B               90
66      No diabetes Treatment A               91
166     No diabetes Treatment B               91
86      No diabetes Treatment A               92
186     No diabetes Treatment B               92
98      No diabetes Treatment A               95
198     No diabetes Treatment B               95
44      No diabetes Treatment A               96
144     No diabetes Treatment B               96
51      No diabetes Treatment A               97
151     No diabetes Treatment B               97
27      No diabetes Treatment A               99
127     No diabetes Treatment B               99
53      No diabetes Treatment A              100
153     No diabetes Treatment B              100
```
