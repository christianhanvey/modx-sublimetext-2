# MODx Sublime Text 2 Bundle

This bundle aims to provide most of MODx functionality and features when creating Custom Manager Pages.

It also provides code-snippets for some common snippets and their properties - currently for getResources, Wayfinder and FormIt.

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

####  Wayfinder

trigger: _Wayf_

Provides a Wayfinder snippet call with only a few properties. You are encouraged to customise your own version of this, based on the full version below.

	[[wayfinder?
		&startId=``
		&level=`0`
		&limit=`0`
		&includeDocs=``
		&excludeDocs=`0`
		&sortBy=``
		&sortOrder=`ASC`
		&where=`[{"class_key:!=": "Article"}]`
		&outerTpl=``
		&rowTpl=``
		&parentRowTpl=``
		&parentRowHereTpl=``
		&hereTpl=``
		&innerTpl=``
		&innerRowTpl=``
		&innerHereTpl=``
		&activeParentRowTpl=``
	]]


trigger: _Wayfinder_

Provides a Wayfinder snippet call with all properties and sample/default values. The first tab will highlight the entire line for each snippet property so it can quickly be removed if not required, alternatively a second tab will place you in the property value field.


	[[wayfinder?
		&startId=``
		&displayStart=`0`
		&level=`0`
		&limit=`0`
		&ignoreHidden=`0`
		&ph=`0`
		&debug=`0`
		&hideSubMenus=`0`
		&removeNewLines=`0`
		&textOfLinks=`menutitle`
		&titleOfLinks=`pagetitle`
		&rowIdPrefix=`0`
		&useWeblinkUrl=`1`
		&includeDocs=``
		&excludeDocs=`0`
		&cacheResults=``
		&cacheTime=`3600`
		&contexts=``
		&startIdContext=``
		&config=``
		&scheme=`-1`
		&sortBy=``
		&sortOrder=`ASC`
		&where=`[{"class_key:!=": "Article"}]`
		&hereId=``
		&hereTpl=``
		&firstClass=``
		&lastClass=`last`
		&hereClass=`active`
		&selfClass=``
		&parentClass=`parent`
		&rowClass=``
		&levelClass=``
		&outerClass=``
		&innerClass=``
		&webLinkClass=``
		&cssTpl=``
		&jsTpl=``
		&outerTpl=``
		&rowTpl=``
		&parentRowTpl=``
		&parentRowHereTpl=``
		&hereTpl=``
		&innerTpl=``
		&innerRowTpl=``
		&innerHereTpl=``
		&activeParentRowTpl=``
		&categoryFoldersTpl=``
		&startItemTpl=``
	]]




####  FormIt

trigger: _FormIt_

Provides a snippet call for FormIt. The first tab will highlight the entire line for each snippet property so it can quickly be removed if not required, alternatively a second tab will place you in the property value field.


	[[FormIt?
		&hooks=``
		&preHooks=``
		&submitVar=``
		&validate=`username:required,email:email:required`
		&validationErrorMessage=`<p class="error">A form validation error occurred. Please check the values you have entered.</p>`
		&validationErrorBulkTpl=`<li>[[+error]]</li>`
		&errTpl=`<span class="error">[[+error]]</span>`
		&customValidators=``
		&clearFieldsOnSuccess=`1`
		&store=`0`
		&storeTime=`300`
		&placeholderPrefix=`fi.`
		&successMessage=``
		&successMessagePlaceholder=`fi.successMessage`
		&redirectTo=``
	]]



trigger: _FormItemail_

	[[FormIt?
		&hooks=`spam,email,redirect`
		&preHooks=``
		&submitVar=``
		&validate=`username:required,email:email:required`
		&validationErrorMessage=`<p class="error">A form validation error occurred. Please check the values you have entered.</p>`
		&validationErrorBulkTpl=`<li>[[+error]]</li>`
		&errTpl=`<span class="error">[[+error]]</span>`
		&customValidators=``
		&clearFieldsOnSuccess=`1`
		&store=`0`
		&storeTime=`300`
		&placeholderPrefix=`fi.`
		&successMessage=``
		&successMessagePlaceholder=`fi.successMessage`
		&redirectTo=``
		emailTpl=``
		emailSubject=``
		emailUseFieldForSubject=``
		emailTo=``
		emailToName=``
		emailFrom=``
		emailFromName=``
		emailHtml=``
		emailConvertNewlines=``
		emailReplyTo=``
		emailReplyToName=``
		emailCC=``
		emailCCName=``
		emailBCC=``
		emailBCCName=``
		emailMultiWrapper=``
		emailMultiSeparator=``
	]]


