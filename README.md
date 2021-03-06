# Krakenous

Krakenous is a Python "backend" for machine-learning tasks. It provides various storage options (currently,
SQLite as a backend is implemented), and a lot of helper methods/functions. Designed to help with Kaggle
competitions.

# Why?

Because time spent on organizing data loading/storage can be spent doing more interesting things (like
writing complex functions to classificate squids based on hi-res photos of their tentacle-thingies). You write the
data/feature-extracting functions, Krakenous takes care of writing them to disk.

Why "Krakenous"? Krakens are awesome, and "krakenous" would make one hell of an adjective.

# What can it do?

Store data. Extract features and store them (you'll have to write the extractor function yourself).
You can call do something like:

```python
mydataset.extract_feature_simple(some_data_feature_extractor_function, ('filename', ))
```

and it will extract and store the feature for the whole dataset. It comes with helper functions to build base
datasets from CSV files, files in folders (for example - images in folders), convert things into numpy arrays.
You can work as a team, too - Krakenous supports basic merging of different datasets (Alice extracts some of the features,
Bob extracts some other features, they combine their datasets and save time).

It is modular - you can plug in your own serializers, functions to create the initial dataset (search for files in folders,
parse CSV, whatever you need). Even writing your own backend is not that hard (probably).

# What will it be able to do?

Support more backend types, export to CSV.

# Changelog

## v0.3 (Squishable Squid Eyeball)

**v0.3 (08.01.2015)** Added some additional methods, major cleanup in the ``DataSet`` class. Shelve has been deprecated
as a backend, only SQLite support for now. The ``yield_data_records`` method now utilizes ``WHERE`` clauses in the backend
and so should work faster. Fixed error when attempting to deserialize a non-existent record (serializer fails
on ``None``), this should help work with Null values (probably, not tested yet).

## v0.2 (Charismatic Octopii)

**v0.2.1 (06.01.2015)** Fixed imports and renamed source folder

**v0.2 (05.01.2015)** The first more-or-less stable version. No docstrings yet. Serialization / deserialization support,
probably more-or-less stable function signatures and some working pre-rolled functions are in place.

## v0.1 (Tentacleous Chaos)

This was a development version - with everything-breaking changes pushed daily (hourly, even).
Writing a specific changelog of things that have changed between v0.1 and v0.2 would be about as much use as
documenting pure primordial chaos. Sorry.