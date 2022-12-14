Indigo DAO
==========

[![License: CC BY-SA
4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-sa/4.0/)

The Indigo DAO owns and manages the Indigo Protocol. This repository
maintains documents relating to the Indigo DAO. They are free culture
work, licensed under Creative Commons Attribution Share-Alike (CC-BY-SA)
Version 4.0.

Indigo Protocol is a synthetics platform deployed on the Cardano
blockchain. It connects the real-world to the blockchain, giving
everybody equal access to financial opportunities.

For more information about Indigo, visit the [Indigo Protocol
website](https://indigoprotocol.io/).

Documents
---------

This repository stores two documents:

1.  **Indigo DAO Constitution** -- describes the rules set forth and
    adopted by the Indigo DAO Members
2.  **Indigo DAO Voting Procedures** -- describes the processes and
    procedures that apply to any vote for the Indigo DAO

Usage
-----

To generate the PDF files yourself, you can use `pdflatex`:

    pdflatex --shell-escape constitution.tex

These documents are intended to be recorded on-chain after the launch of
Indigo Protocol. More information about how to verify documents on-chain
will be provided after Indigo Protocol mainnet launch.

Verifying Authenticity
----------------------

Each time a PDF is generated by `pdflatex` the metadata may change.
Metadata can include information such as bookmarks (making the table of
contents clickable, for example). This can cause the checksum of the
document to differ between compiles even if content hasn't changed.

To remove metadata, `mat2` can be used. After removing metadata you can
verify the checksum of the document against a reference.

    $ mat2 constitution.pdf && sha256sum constitution.cleaned.pdf
    5ee5f032c90893a35ffe75c2d35e0a0d71fad9292360ae3fe1052efef896689a  constitution.cleaned.pdf

    $ mat2 voting-procedures.pdf && sha256sum voting-procedures.cleaned.pdf
    2a5f3002c93a8ae98db2db57353707a26808ce6fbced75232f4464af1fd53639  voting-procedures.cleaned.pdf

If checksums of two files match after removing the metadata, then the
two files are verified to be equivalent, therefore no content has
changed. If the checksums differ, then the content has been altered.
