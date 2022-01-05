# Python basics with examples from research in atmospheric sciences

When I started learning Python, sometimes I did not fully understand why a certain term is introduced (e.g. "string", "dictionary", "tuple" and "loops"), and how is this related to my research. Another challenge was to develop codes needed in real research only based on very basic examples in many existing tutorials. So here I use examples from atmopsheric sciences research to introduce fundamentals of Python. More details will be provided in Jupyter Notebooks, for now I show some examples below:

#### What is a "Dictionary"?
```
# construct a simple dictionary to store full names for NO2 and SO2
gases = {'NO2': 'nitrogen dioxide',
         'SO2': 'sulfur dioxide'}

print(gases)           # check the results
print(type(gases))     # check the "type" so now you confirm that this is a Python dictionary
print(gases.keys())    # check the "keys" (short names of NO2 and SO2)
print(gases.values())  # check the "values" (long names of NO2 and SO2)
```

#### What can I do with a "Dictionary"?
```
# here short names and long names of a few air pollutants are provided in two lists
short_name = ['NO2','SO2','CO','O3','PM2.5']
long_name  = ['nitrogen dioxide', 'sulfur dioxide', 'carbon monoxide', 'ozone', 'particulate matter 2.5']

# you can store them in a single dictionary
# you can type the dictionary manually like the above example or use a "loop"
pollutants = {}

for i in range(len(short_name)):
    dict1 = "{}".format(short_name[i])
    dict2 = "{}".format(long_name[i])
    pollutants[dict1]=dict2

# now let's see what we can do with a dictionary
print(pollutants)                   # look at the whole dictionary
print('SO2' in pollutants)          # check if "SO2" is in dictionary
print(pollutants['SO2'])            # look up for the long name of "SO2" 
pollutants['HCHO'] = 'formaldehyde' # add one more pollutant to the dictionary
del pollutants['NO2']               # remove "NO2" from the dictionary
print(pollutants)                   # look at the whole dictionary again to check the updates
```

#### How to use "for loops" and "if statements" in real research?
```
# an example of "for loops" from a generic Python tutorial
fruits = ["apple", "banana", "cherry"]

for x in fruits:
  print(x)
```

```
# an example of "if statements" from a generic Python tutorial
a = 33
b = 200

if b > a:
  print("b is greater than a")

```

```
# use "for loops", "if statements" and the operator "&" in real research

# imagine there is a dataframe (df) with three columns: lattitude (lat), longitude (lon) and a variable (var)
# and you want to print out values of this variable within a specific domain, then you can do:
for i in range(df.shape[0]):
    if ((df['lat'][i] > 35) &
        (df['lat'][i] < 40) &
        (df['lon'][i] > 50) &
        (df['lon'][i] < 60)):
        print(df['lat'][i],df['lon'][i],df['var'][i])
```
