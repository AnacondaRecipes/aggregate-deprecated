About the AnacondaRecipes/aggregate-deprecated repository
=========================================================

The aggregate-deprecated repository is roughly similar to the concept of the ``aggregate`` repository.  Feedstocks having here their last resort, if they are no longer maintained on ''aggregate''.

Please look at [deprecated.csv](deprecated.csv) file for information.

How to deprecate a package
==========================

When a package is no longer a focus for Anaconda, it should be moved to the depprecation list.

The process starts by adding the feedstock to
the aggregate-deprecated feedstock and documenting
the reason in the deprecated.csv file.  In the deprecated.csv file
When adding a feedstock, please add it via a branch so it can get reviewed.

After the PR is approved by the appropriate people, please proceed to remove
from the aggregate repo.

How to do add to aggregate-deprecated:
```
cd aggregate-deprecated
git pull
git checkout -b deprecations/2023-06-29
<your preferred text editing tool for documenting package/feedstock, date and reason> deprecated.csv
```

How to remove from aggregate:
```
git submodule deinit -f salt-feedstock
rm -rf .git/modules/salt-feedstock
git rm -f salt-feedstock
git commit -m "Deprecating salt-feedstock."
git push
```