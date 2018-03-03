# sendmail project

This project currently tested with [emailjs](https://www.npmjs.com/package/emailjs) and [catatnight/postfix](https://hub.docker.com/r/catatnight/postfix/). If you tested with [nodemailer](https://www.npmjs.com/package/nodemailer) you should consider the __tls__ property in the option.  

    var mailtransport = nodemailer.createTransport({
        host: "host of postfix container",
	secure: false
	tls: {
            rejectUnauthorized: false
        },
	auth:{
	    user: "smtp username",
	    pass: "smtp password"
	},
	logger:logger,
	proxy: proxy
    });

Or you will get the following error:  
[Error: DEPTH_ZERO_SELF_SIGNED_CERT](https://stackoverflow.com/questions/28259239/nodemailer-depth-zero-self-signed-cert)

You can give logger and proxy as well. The logger object would be log4js logger object, the proxy would be something like "http://xxx.com:8080"

