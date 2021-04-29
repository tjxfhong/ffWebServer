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
{
	"Version":"1.0.11", /**/
	"Server":"", /*服务器是否可以生成授权码，值为域名加密串，*/
	"ServerAddress":"0.0.0.0", /*"0.0.0.0",定义服务器地址，不定义时默认为空，空支持所有域名*/
	"ServerPort":"8000", /*定义服务器端口号，只能是整数，不定义时默认为80，80端口为服务器系统默认HTTP端口，如端口已占用，可自定义一个空闲的端口*/
	"Scheme":"http", /*是否HTTPS，HTTPS时HTTP请求会转向HTTPS，服务器只可以一个HTTPS网站，文件在服务器文件同目录下*/
	"HttpsPort":"8443", /*HTTPS服务器端口号，只能是整数，不定义时默认为443，Scheme=https时有效，443端口为服务器系统默认HTTPS端口，如端口已占用，可自定义一个空闲的端口*/
	"VirtualHost":{ /*这里定义虚拟主机，*/
		"localhost":{ /*这里定义了第一个使用本机的虚拟主机，定义其它主机时，复制这个进行修改，避免丢失字段出错*/
			"ServerAdmin":"yourname@localhost", /*ServerAdmin = 服务器管理员用户名*/
			"ServerPass":"password", /*ServerPass = 服务器管理员密码*/
			"Endtime":"2030-07-30", /*Endtime = 网站停止时间*/
			"Suspend":"enable", /*Suspend = 网站状态，enable表示启用,disabled表示停用*/
			"Domain":["localhost"], /*Domain = 域名组，多个域名用,分隔*/
			/*以下改到用户网站设置文件内，或改为注册用户时定义*/
			"iscomp":"1",/*是否压缩图片，1=是，0或其它=否*/
			"sourimg":"0",/*是否保留原图，1=是，0或其它=否，iscomp=1时有效*/
			"comps":["1000","300"],/*要压缩的宽的数组，例：["1000","300"]，iscomp=1时有效*/
			"compq":"60",/*压缩图片的质量，0-100 | 60，75，90，100，默认75，iscomp=1时有效*/
			"DocumentRoot":"C:/website/zs.ffwish.com\\", /*DocumentRoot = 网站根目录*/
			"Database":"C:/website/zs.ffwish.com/db", /*Database = 文件数据库所在的目录，SQLITE时，存放数据库文件的位置*/
			"dbdriver":"mysql", /*dbdriver = 数据库驱动，支持的数据库有：mysql、sqlite、postgresql*/
			"dbname":"ffwbms_zs", /*dbname = 数据库名，mysql、sqlite时有效*/
			"dbcharset":"utf8", /*dbcharset = 数据库字符编码*/
			"dbusername":"ffwbms_zs", /*dbusername = 数据库用户名，mysql时有效*/
			"dbpassword":"ffwbms_zstjhd", /*dbpassword = 数据库用户密码，mysql时有效*/
			"dbprotocol":"tcp", /*dbprotocol = 数据库连接协议，tcp，mysql时有效*/
			"dbaddress":"rm-bp1cs63553t6s64be7o.mysql.rds.aliyuncs.com", /*dbaddress = 数据库服务器地址或IP，mysql时有效*/
			"dbport":"3306", /*dbport = 数据库服务器端口，mysql时有效*/
			/*以上改到用户网站设置文件内*/
			"ErrorLog":"error.log", /*ErrorLog = 错误日志文件，放入logs目录下*/
			"CustomLog":"access.log", /*CustomLog = 访问日志文件，放入logs目录下*/
			"Explain":"这是本机测试网站" /*Explain = 网站说明*/
		}
}
