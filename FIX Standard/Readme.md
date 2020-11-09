# FIX Standards

These Orchestra files are snapshots of versions of the FIX protocol that are still supported. 

* FIX 4.2
* FIX 4.4
* FIX Latest

Orchestra files for incremental updates to the FIX standard, called extension packs, will be published periodically as FIX Latest. Extension pack files including gap analysis documents are available at [FIX Extension Packs](https://www.fixtrading.org/extension-packs/).

## Generation

The FIX 4.2 and 4.4 files were translated from FIX Unified Repository 2010 Edition into the Orchestra schema. Since the old Repository format only described message structures, these translations are limited to that content, without scenarios or workflows. 

### Translation Notes

* In FIX 4.2, repeating groups were defined in-line in message definitions. They had no identities of their own. To translate them to Orchestra schema, where group ID and name are required, they were matched up with corresponding definitions in later versions of FIX by the containing message type and the group's NumInGroup tag. The ID and name of the matching group was then used, although no such identity actually existed in the FIX 4.2 Repository.
* In a few cases, the same repeating group was defined in different messages in the FIX 4.2 Repository. In translating to Orchestra, the repeating groups were manually deduplicated.
* In at least one case, a repeating group changed its NumInGroup tag going from FIX 4.2 to 4.3 and later versions, and other radical changes were made. Therefore, some correspondance between FIX 4.2 and later versions is approximate.

Some analysis posted by Hanno Klein:

> SecurityDefinition(35=d) apparently went through major changes more than once from FIX 4.2 to 4.3 and then again to 4.4. Fields for underlying instruments were present in 4.2, absent in 4.3 and back again in 4.4, albeit as part of different repeating groups. Also, Side(54) was part of that repeating group in FIX 4.2 and no longer part of it in FIX 4.4. RatioQty(319) was also part of the group in FIX 4.2 and "vanished" with FIX 4.3. In short, the group that existed in FIX 4.2 is unique to FIX 4.2 and was removed as of FIX 4.3. UndInstrmtGrp may look similar in FIX 4.4 but should be viewed as a different group.

> In general it is not an issue to have a NumInGroup field like 146 with different content, i.e. the NumInGroup field does not identify a repeating group. The repeating groups did not have names in FIX 4.2.

## Maven

This resource is available through Maven central repository as

```xml
<dependency>
  <groupId>io.fixprotocol.orchestrations</groupId>
  <artifactId>fix-standard</artifactId>
  <version>1.5.1</version>
</dependency>
```