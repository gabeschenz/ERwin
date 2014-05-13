ERwin
=====

Erwin scripts and other tools.

This project is simply a collection of and templates to help with working with ERwin data models.  

Pre- and Post-Scripts
----------------------
The pre- and post-scripts have a standard naming convention as follows:
  `platform.[model|table].[pre|post]script.purpose`

Note that anything with a platform of `generic` should work with any targeted platform.  YMMV.  

Currently, I have:
 - generic.model.prescript.create_backup:
 	For each table in a forward engineering effort, this will create a backup of a given table as _schema.tablename\_BKP\_YYYY\_MM\_DD
 - vertica.table.prescript.drop_table:
    This will create a drop table statement in the form of _drop table if exists schema.tablename_.
 - vertica.table.postscript.create_projections:
    This will create a superprojection for each table in the forward engineering effort.  This will segment the projection on the primary key.

Forward Engineering Templates:
------------------------------
The following forward engineering templates are currently available:
 - Netezza
 
    There is one table UDP which need to be created for use with this FET:
 	 - DistributionKey
 	 
   This should have a default value of "random".  Otherwise provide the relevant column names in the appropriate places, and it should generate accordingly.

 - Vertica
 
	There are three table UDPs which need to be created for use with this FET:
 	 - OrderBy
 	 - PartitionBy
 	 - SegmentedBy
 	 
  Each of these should have a default value of "None".  Otherwise provide the relevant column names in the appropriate places, and it should generate accordingly.

