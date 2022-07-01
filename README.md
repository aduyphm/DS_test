# DS_test
T6 - fix 'Câu 2':
```def get_subseq_limit(A, k):
  # YOUR CODE START 
  L = np.zeros(len(A))
  pos = np.zeros(len(A))
  min = A[0]
  L[0] = 0
  for i in range(1, len(A)):
    if i - pos[i] >= k: 
      pos[i] = i - k + 1
      min = A[int(pos[i])]
    if L[i] < A[i] - min:
      L[i] = A[i] - min
    if A[i] < min:
      min = A[i]
      pos[i:len(A)] = np.full(len(A)-i,i)
  max = 0
  s = 0
  e = 0
  for i in range(len(A)):
    if L[i] > max:
      max = L[i]
      s = int(pos[i])
      e = i
  a = A[s:e+1]
  # / END YOUR CODE
  return a
```
