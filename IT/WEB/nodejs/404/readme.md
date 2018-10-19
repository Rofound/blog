# 处理页面404页面显示
const fs = require(fs);
const errorLogUrl = './views/portal/404.html';

way 1:
fs.exists(errorLogUrl, (exists)=>{
   exists? fs.unlinkSync(errorLogUrl): exists;
   console.log('---------\n', exists);
});

way 2:
const fd = fs.openSync(errorLogUrl, 'r+');
fs.ftruncate(fd, 0, function(err){
    console.log('---------\n', err);
});

const errorLogFile = fs.createWriteStream(errorLogUrl, {encoding: 'utf-8', mode: 0o666, flags: 'w'});
errorLogFile.write(resp.body);
errorLogFile.end();