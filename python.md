### formatters and using `str.format(value1, value2, ...)`
- placeholders using named indexes -> `{price}`, numbered indexes->`{0}`, and empty placeholders `{}`
  - `My name is {fname}, I'm {age}".format(fname = "John", age = 36)`
  - `"My name is {0}, I'm {1}".format("John",36)`
  - `"My name is {}, I'm {}".format("John",36)`
- formatting types, inside `{}`
  - `:,` uses comma as thousands separator, results 100,000
  - `:.0f` no floating point values, results 4
  - `:.1%` percent with one decimal, results 3.4%


### `__init__.py`
  - package types
    - regular packages
      - traditional packages (python 3.2 or earlier)
      - a directory containing `__init__.py` file
      - when a regular package is imported, `__init__.py` is implicitly executed, objects are bound to names in the package's namespace 

```py
if __name__ == "__main__":
    print("Hello, World!")
```
- protects from accidentally invoking the script
- when the main python code is executed from terminal, `__name__ = "__main__"`
- but if its (foo.py) imported from another python file, `__name__ = "foo"`


### different file formats that you can save
- if you cast the datatype in dataframe, you'll reduce the size
- when you save as csv and read it back in, you loose information about the dtypes
  - you can add the metadata again using dtypes in read_csv
- when the dataset is very big
- pickle
  - use `df.to_pickle()`
  - faster, smaller and metadata is not lost

- parquet (faster and smaller)
  - `pip install pyarrow`
  - `pip install fastparquet`

- feather (faster than parquet, but a little bit larger than parquet)