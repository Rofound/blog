# express 4.16.0
## Have to 
- http://expressjs.com/zh-cn/resources/middleware.html
- https://bignerdcoding.com/archives/43.html

## The middleware error handle for static file
    res.status(404);
    var options = {
        encoding: 'utf-8'
    };
    fs.readFile(__dirname + '/views/portal/404.html', options, function(err, data){
        res.send(data);
        res.end();
    });

## The "express" of version is 4.8.0 supports sendfile or sendFile
    res.sendfile(__dirname + '/views/portal/404.html');

## use the last error handle middleware function(err, req, res, next)
    app.use(function(err, req, res, next){
        res.status(404);
        utils.render_html(res,'404.html',{});
        res.render('404.html');
    });

## response time calculation
    req._startTime = new Date(); // 获取时间 t1
    var calResponseTimeForFinish = function () {
       var now = new Date(); //获取时间 t2
       var deltaTime = now - req._startTime;
       console.log(resp.statusCode);
       console.log(resp.statusMessage);
       console.log(req.method);
       // The host include port
       console.log(req.url);
       console.log(req.headers.host);
       console.log('Finish : '.concat(deltaTime, 'ms'));
    };
    var calResponseTimeForClose = function () {
       var now = new Date(); //获取时间 t2
       var deltaTime = now - req._startTime;
       console.log('Close : '.concat(deltaTime, 'ms'));
    };
    resp.once('finish', calResponseTimeForFinish);
    resp.once('close', calResponseTimeForClose);

## 