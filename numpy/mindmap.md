- Basic concept
  - compared to python sequence
    - ndarray: same data type 


- Create numpy array 
  - From other data type 
    - df.to_numpy()
      - DataFrame 
  - Numpy specified array 
    - np.arange(start, stop, step)
      - [start, stop)
    - np.zeros(shape)
    - np.ones(shape)
    - np.eye()
    - np.diag(v, k)
  - Numpy random array 
    - np.random.random()
      - [0,1)
    - np.random.uniform()


- Basic Operation
  - np.diff(a, n=1, axis=-1)
    - difference with itself of n element shifted
  - np.sign()
  - np.mean()
    - arithmetic mean 
  - np.average()
    - can have weight 
  - np.cumsum()


- Find index
  - np.where()
  - np.argmax()
  - np.argmin()


- Array transformation
  - array.flatten()
    - make a copy 
  - array.ravel()
    - get a view of the org array 
  - np.pad(array, pad_width)