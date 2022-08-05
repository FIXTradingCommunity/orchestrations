# Known Issues for FIX 4.2 and FIX 4.4

## Introduction

FIX 4.2 and FIX 4.4 are supported legacy versions of the FIX application layer standard. Their meta-data was published in the legacy repository formats (Basic and Unified). Orchestra files are provided for these legacy versions but they are kept in sync with the legacy representations. Known issues with FIX 4.2 and FIX 4.4 that have been corrected in later versions are being listed in the following sections.

## FIX 4.4 datatype error for MassCancelRejectReason(532)

FIX 4.4 defines "char" as datatype for MassCancelRejectReason(532). This has been corrected to "int" as of FIX 5.0.

The issue has been resolved in the Orchestra representation of FIX Latest (https://fiximate.fixtrading.org/). The Orchestra representation of FIX 4.4 will not be updated here to ensure consistency with the legacy repository representations (basic and unified) provided on the FIX website (https://www.fixtrading.org/standards/fix-repository/). Users who need to support the 2-digit standard values or user-defined values of 100 or above, should make changes to their repository to resolve this issue in their own environment. See https://github.com/FIXTradingCommunity/orchestrations/issues/21 for details.
