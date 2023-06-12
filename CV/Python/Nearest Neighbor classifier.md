```python
# for each test image : find closest train image and predict labe of nearest image
import numpy as np
class NearestNeighbor:
	def _init_(self):
		pass
		
	def train(self,X,y):
		self.Xtr=X
		self.ytr=y
		
	def predict(self,X):
		num_test=X.shape[0]
		Ypred=np.zeros(num_test,dtype=self.ytr.dtype)
		#for i in xrange(num_test): # py2 return a generation obj
		for i in range(num_test)    #py3 return a generation obj could save memroy
			distances=np.sum(np.abs(self.Xtr - X[i,:]),axis=1)
			min_index=np.argmin(distances)
			Ypred[i]=self.ytr[min_index]
		return Ypred
```