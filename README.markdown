# MODx Sublime Text 2 Bundle

This bundle aims to provide most of MODx functionality and features when creating Custom Manager Pages.

It also provides code-snippets for some common snippets and their properties - currently only for getResources.

Here is a list of triggers currently setup and in their own context.

### ExtJS - source.js

trigger: _extExtend_

	Ext.extend(MyClass.window.Name, ClassToExtend, {});

trigger: _extReg_

	Ext.reg('myclass-window-name', MyClass.window.Name);

trigger: _extText_

	{
		xtype: 'textfield'
		,fieldLabel: 'label'
		,name: 'name'
		,anchor: '100%'
	}

trigger: _extFun_

	Namespace.window/grid/panel/tree/page/combo/config.ClassName = function (config) {
		config = config || {};
		Ext.applyIf(config, {
			title: 'title'
			,url: connectorUrl
			,fileUpload: true
			,baseParams: {
				action: 'create'
			}
			,fields: []
		});
		Namespace.window/grid/panel/tree/page/combo/config.ClassName.superclass.constructor.call(this, config);
	};
	Ext.extend(Namespace.window/grid/panel/tree/page/combo/config.ClassName, Ext/MODX.Class});
	Ext.reg('namespace-window/grid/panel/tree/page/combo/config-classname', Namespace.window/grid/panel/tree/page/combo/config.ClassName);

### xPDO - text.xml

trigger: _aggregate_

	<aggregate alias="Alias" class="ClassName" local="local" foreign="id" cardinality="one|many" owner="foreign|local" />

trigger: _composite_

	<composite alias="Alias" class="ClassName" local="local" foreign="id" cardinality="one|many" owner="foreign|local" />

trigger: _field_

	<field key="name" dbtype="varchar" precision="160" attributes="unsigned" phptype="string" null="false" default="" />

trigger: _field.int_

	<field key="name" dbtype="int" precision="11" attributes="unsigned" phptype="integer" null="false" default="" />

trigger: _field.enum_

	<field key="name" dbtype="enum" precision="'db','cookie','redis'" phptype="string" null="false" default="" />

trigger: _field.float_

	<field key="name" dbtype="float" precision="8,2" phptype="float" null="false" default="" />

trigger: _model_

	<model package="ClassName" baseClass="xPDOObject" platform="mysql" defaultEngine="MyISAM">

	</model>

trigger: _object_

	<object class="ClassName" table="table_name" extends="xPDOSimpleObject">
		<field key="name" dbtype="varchar" precision="160" attributes="unsigned" phptype="string" null="false" default="" />
	</object>



### snippets - text.html, text.html5, text.plain

####  getResources

trigger: _getR_

Provides a getResources snippet call with only a few properties. You are encouraged to customise your own version of this, based on the full version below.

	[[getResources?
		&parents=``
		&depth=`0`
		&tpl=``
		&resources=``
	]]

trigger: _getResources_

Provides a getResources snippet call with all properties and sample/default values. The first tab will highlight the entire line for each snippet property so it can quickly be removed if not required, and a second tab will place you in the property value field.

	[[getResources?
		&parents=``
		&depth=`0`
		&tpl=``
		&resources=``
		&depth=`10`
		&tplOdd=``
		&tplFirst=``
		&tplLast=``
		&tpl_{n}=``
		&context=``
		&tvFilters=`filter2==one,filter1==bar%||filter1==foo`
		&tvFiltersAndDelimiter=`&&`
		&tvFiltersOrDelimiter=`|OR|`
		&where=`{{"alias:LIKE":"foo%", "OR:alias:LIKE":"%bar",{"OR:pagetitle:=":"foobar", "AND:description:=":"raboof"}}`}
		&sortby=`{"publishedon":"ASC","createdon":"DESC"`}
		&sortbyTV=``
		&sortbyTVType=`string`
		&sortbyAlias=``
		&sortbyEscaped=`0`
		&sortdir=`DESC`
		&sortdirTV=`DESC`
		&limit=`5`
		&offset=`0`
		&dbCacheFlag=`0`
		&according=`0`
		&includeContent=`0`
		&includeTVs=`0`
		&includeTVList=``
		&prepareTVs=`1`
		&prepareTVList=``
		&processTVs=`0`
		&processTVList=``
		&tvPrefix=`tv.`
		&idx=`1`
		&first=`1`
		&last=``
		&outputSeparator=`"\n"`
	]]








