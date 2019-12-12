# DASH-IF Identifier Registry

This repository collects the list of existing identifiers, however it does not
act as an registration authority. Requests for adding an identifier are
formally submited via a Pull Request here. The simplest way to submit a Pull
Request is described bellow.

## Submission process

1. Login on GitHub using your personal account (create one if needed)
2. Fork the repository into your own area at GitHub
3. Go to that fork, and edit the CSV files in the folder /csv according to your submission (e.g. adding, removing identifiers ...)
4. When it is right, submit a Pull Request the repository here.

## Guidelines for CSV formatting (step 3)

The identifers are grouped per type in different CSV files. Each line of 
the CSV files is composed of exactly 5 fields following the same pattern
`identifier|specification|url|section|comment`.

- `identifier`: the identifier
- `specification`: name and version of the corresponding specification, e.g. ISO/IEC 23009-1
- `url`: link to the corresponding specification/company/product/etc...
- `section`: relevant section in the corresponding specification, if not applicable, the field must be present but emtpy
- `comment`: free form comment related to the identifier

To make a valid Pull Request, it boils down to:

1. Choosing the right CSV file corresponding to your identifier
2. Modifying the chosen CSV file with your proposed identifier according to the patter above
3. Committing your changes
4. Submitting the Pull Request

## Maintainer

Whenever there is a commit added to this repository, it triggers the CI script
.travis.yml. This script execute a HTTP call to trigger the DASH-IF website
build script. This call is sent to the Travis CI API. The call to the API is
authenticated using a Travis Token of someone having access permission to the
DASH-IF website repository build on Travis. The Token is insert into the script
using the key TRAVIS_TOKEN.
