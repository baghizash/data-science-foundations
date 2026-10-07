# Course 6 "Statistics and Clustering in Python" - Kunci Jawaban

## Week 1 Summative Assessment (15 soal, 40 menit)
1. print(ages[1+3]) | print(ages[-1])
2. print(age)
3. ages = [34, 55, 89, 10]
4. sum(ages)
5. high-level | performant | well-tested
6. mean | average | standard deviation | median
7. someone else may check calculations; clearer code helps | when returning later, waste less time re-understanding
8. because SD measures magnitude of difference, sign doesn't matter
9. x = 10
10. x | my_age
11. population = all elements of the group studied; sample = part used to describe the group
12. more practical
13. population = all Victoria High freshmen, sample = 150 selected students
14. Σx = 176 | x̄ = 176/6 = 29.3
15. x̄ = 70 | Σ(xi−x̄)² = 850 | s² = 850/3 = 283.3 | s = √283.3 = 16.83

## Week 2 Summative Assessment (17 soal, 40 menit)
1. import
2. the x coordinates then the y coordinates
3. True
4. [2,4,6]
5. data[:,1] | [data[0][1], data[1][1], data[2][1]] | data[:,-1]
6. No, it averages all values ignoring columns
7. data.mean(0) | np.mean(data, 0)
8. Call scatter() multiple times with different datasets
9. subplots() returns two things assigned to two variables
10. patches
11. True
12. np.linalg.norm
13. np.sqrt(np.sum((x1−x2)*(x1−x2))) | np.linalg.norm(x1−x2)
14. lets you apply a function to every item in a list
15. np.sqrt
16. normed = (values[0]−np.min(values)) / (np.max(values) − np.min(values))
17. np.min(data, 0)

## Week 3 Summative Assessment (15 soal, 40 menit)
1. read_csv
2. data['spare_cash'] | data["spare_cash"] | data.spare_cash
3. access a row by integer index
4. the DataFrame on which sort_values() is called is re-organised
5. data[data['avg_income'] < 10000]
6. data.iloc[0]
7. the pyplot module in matplotlib
8. plt.text(y=36,x=56,s='London') | plt.text(56,36,'London') | plt.text(s='London', y=36,x=56)
9. the integer index of each row
10. A list comprehension
11. low income but high happiness
12. alpha
13. s
14. algorithms can operate in higher spatial dimensions than our eyes
15. k sets the number of cluster centres sought

## Week 4 Summative Assessment (4 soal, 15 menit) - SELF-REPORT
Jawaban tergantung pengerjaan project banknote-nya sendiri:
1. fungsi Python yang dipakai untuk load dataset (lihat kode project)
2. fungsi pyplot yang dipakai untuk visualisasi (centang semua yang dipakai: scatter, xlabel, text, dll)
3. libraries yang dipakai: sklearn.cluster.KMeans | pandas | numpy (jangan centang tigers / nunpy)
4. centang semua bagian yang benar-benar ada di report KECUALI "Your code": Description, Statistical measures, size/features info, recommendations, limitations
