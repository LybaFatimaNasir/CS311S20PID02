# Plagiarism-Checkrista
## Plagiarism checking tool 
### Psuedo Code
```
function printdiff(C[0...m,0...n],x[1...m],Y[1...n],i,j)
if i<0 and j<0
return 
elif i<0
printdiff(C,X,Y,i,j-1)
print "+" + Y[j]
elif j<0
printdiff(C,X,Y,i-1,j)
print "-" + X[i]
elif X[i] == Y[j]
printdiff(C,X,Y,i-1,j-1)
print " " + X[i]
elif C[i][j-1] >= C[i-1][j]
printdiff(C,X,Y,i,j-1)
print "+" + Y[j]
elif C[i][j-1] < C[i-1][j]
printdiff(C,X,Y,i-1,j)
print "-" + X[i]

function diff(X,Y)
C = lcslen(X,Y)
return printdiff(C,X,Y,len(X)-1,len(Y)-1)

**backtrack**(C[0..m,0..n], X[1..m], Y[1..n], i, j) 
 **if** i = 0 or j = 0 
  **return** "" 
 **if** X[i] = Y[j] 
  **return** backtrack(C, X, Y, i-1, j-1) + X[i] 
 **if** C[i,j-1] > C[i-1,j] 
  **return** backtrack(C, X, Y, i, j-1) 
 **return** backtrack(C, X, Y, i-1, j) 

 **lcs**(X[1..m], Y[1..n]) 
 C=lcs(X[1..m], Y[1..n]) 
 **return** backtrack(C[0..m,0..n], X[1..m], Y[1..n],len(X[1..m]-1),len(X[1..m],-1)) 

 

 

