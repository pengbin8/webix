Default.aspx配置
	1.引入  <%@ Page Language="C#" AutoEventWireup="true" CodeBehind="Default.aspx.cs" Inherits="WebixKmo.Default" %>
	2.引入  【webix.js & webix.css require.js】
	3.引入 	【app.js】
app文件夹
	1.assets文件夹  app.css用户自定义css 
	2.libs文件夹	
		1)almond 		文件夹 	https://github.com/requirejs/almond
		2)less		文件夹  https://raw.githubusercontent.com/less/less.js/v2.7.2/dist/less.js  & less.min.js
		3)polyglot	文件夹	https://github.com/airbnb/polyglot.js  download的build目录
		4)requirejs	文件夹	https://raw.githubusercontent.com/requirejs/text/latest/text.js  &  http://requirejs.org/ 下载require.js 85k
		5)routie		文件夹 	https://raw.githubusercontent.com/jgallen23/routie/master/dist/routie.js & routie.min.js
		6)webix		文件夹  http://webix.com/ 下载codebase文件夹
		7)webix-jet	文件夹  https://github.com/webix-hub/jet-core 根目录
	3.locales文件夹  
		=>en.js中文&zh.js英文
			---en.js--
			define([], function () {
				return {
					language: "中文",
				};
			});
			---zh.js--
			define([], function () {
				return {
					language: "chinese",
				};
			});
	4.views文件夹 用户自定义的js文件
		=>main.js
			define(["libs/webix-jet/plugins/locale", "app", "locale"], function (locale, app, _) {
			
		});
	5.app.js文件
		=>
		define([
			"libs/webix-jet/core",
			"libs/webix-jet/plugins/locale",
			"libs/webix-jet/plugins/menu"
		], function (core, locale, menu) {
			var app = core.create({
				id:			"id",
				name:		"name",
				version:	"0.1.0",
				debug:		true,
				start:		"/main/roi.index"
			});
			app.use(locale, { lang: "en" });
			app.use(menu);
			return app;
		});
