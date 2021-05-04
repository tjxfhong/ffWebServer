# ffWebServer
飞鸿网站服务器程序
官网：http://www.ffwish.com 
全部动态语法说明在官网有详细文档

下载后，配置好网站，运行程序即可。

服务器配置网站格式（/*中间为注释*/）：
/*
http://localhost:8000/
服务器定义文件，JSON格式，所有键值都必须是字符串，
目录时尽量使用 / 而不是 \
\为转义，要使用\时，二个一起为一个，如：\\
*/

飞鸿WEB服务器不需要IIS、APACHE、ASP、PHP、JSP等，支持多网站管理，具有底层速度快，对服务器硬件要求低等特点，使用原生HTML+CSS，加上飞鸿网站动态语言，即可以完全实现网站的开发与搭建，支持SQLite、MYSQL和PostgreSQL数据库，简洁的语言语法，很容易就可以学会并上手写出商业化电脑网站、手机网站、APP、微信小程序、百度小程序、OA系统等。

下载飞鸿WEB服务器程序

飞鸿WEB服务器程序的布署：

安装好WINDOWS或LINUX后，下载飞鸿WEB服务器程序，上传到服务器任意目录中，编辑好服务器配置文件(config.json)，运行即可。

服务器配置文件(config.json)定义如下：
<code>
/*
服务器定义文件，JSON格式，所有键值都必须是字符串，
	目录时尽量使用 / 而不是 \
	\为转义，要使用\时，二个一起为一个，如：\\
*/
{
	"Version":"1.0.11", /**/
	"MainDomain": "localhost",/*服务器管理主域名，非主域名不可以使用管理服务器函数*/
	"ServerAddress":"0.0.0.0", /*"0.0.0.0",定义服务器地址，不定义时默认为空，空支持所有域名*/
	"ServerPort":"80", /*定义服务器端口号，只能是整数，不定义时默认为80，80端口为服务器系统默认HTTP端口，如端口已占用，可自定义一个空闲的端口*/
	"Scheme":"http", /*是否HTTPS，HTTPS时HTTP请求会转向HTTPS，服务器只可以一个HTTPS网站，文件在服务器文件同目录下*/
	"HttpsPort":"8443", /*HTTPS服务器端口号，只能是整数，不定义时默认为443，Scheme=https时有效，443端口为服务器系统默认HTTPS端口，如端口已占用，可自定义一个空闲的端口*/
	"VirtualHost":{ /*这里定义虚拟主机，*/
		"localhost":{ /*这里定义了第一个使用本机的虚拟主机，定义其它主机时，复制这个进行修改，避免丢失字段出错*/
			"ServerAdmin":"username", /*ServerAdmin = 服务器管理员用户名，暂时未使用*/
			"ServerPass":"password", /*ServerPass = 服务器管理员密码，暂时未使用*/
			"Endtime":"2030-07-30", /*Endtime = 网站停止时间*/
			"Suspend":"enable", /*Suspend = 网站状态，enable表示启用,disabled表示停用*/
			"Domain":["localhost"], /*Domain = 域名组，多个域名用,分隔，例："site1.com","www.site1.com"*/
			"iscomp":"1",/*是否压缩图片，1=是，0或其它=否*/
			"sourimg":"0",/*是否保留原图，1=是，0或其它=否，iscomp=1时有效*/
			"comps":["1000","300"],/*要压缩的宽的数组，例：["1000","300"]，iscomp=1时有效*/
			"compq":"75",/*压缩图片的质量，0-100 | 60，75，90，100，默认75，iscomp=1时有效*/
			"DocumentRoot":"C:/website/test1", /*DocumentRoot = 网站根目录*/
			"Database":"C:/website/test1/db", /*Database = 文件数据库所在的目录，SQLITE时，存放数据库文件的位置*/
			"dbdriver":"sqlite", /*dbdriver = 数据库驱动，支持的数据库有：mysql、sqlite、postgresql*/
			"dbname":"ffwbms.ffs", /*dbname = 数据库名，mysql、sqlite时有效*/
			"dbcharset":"utf8", /*dbcharset = 数据库字符编码*/
			"dbusername":"", /*dbusername = 数据库用户名，mysql时有效*/
			"dbpassword":"", /*dbpassword = 数据库用户密码，mysql时有效*/
			"dbprotocol":"", /*dbprotocol = 数据库连接协议，tcp，mysql时有效*/
			"dbaddress":"", /*dbaddress = 数据库服务器地址或IP，mysql时有效*/
			"dbport":"", /*dbport = 数据库服务器端口，mysql时有效*/
			"ErrorLog":"error.log", /*ErrorLog = 错误日志文件，放入logs目录下*/
			"CustomLog":"access.log", /*CustomLog = 访问日志文件，放入logs目录下*/
			"Explain":"这是本机测试网站" /*Explain = 网站说明*/
		}
	}
}
</code>
飞鸿WEB服务器内含默认SQLite取值函数近200个，如果使用通用企业网站，可以直接使用。

