### nginx
#How to install nginx on mac  

#1. 用brew 安裝# 
    <pre>$brew intsall nginx</pre>
#2. 進入該目錄#    
   <pre>cd /usr/local/etc/nginx</pre>
   打開 nginx.conf 設定參數(用 <pre>$vim nginx.conf<pre> 開啟)
#3. 設定該檔案路徑#
例如:  root  “/Users/yourusername/Desktop/ExtJs_practice” 和 server{listen:8082 } (註: 不一定要8082)
#4. $nginx (開啟)# 
如果開啟失敗，有可能port 被別的程式使用
#5. 進入頁面 localhost:8082/index.html# 
意思是在網址列輸入localhost:8082/index.html)
如果看到是403 表示沒有權限，因此要設定該檔案權限
輸入<pre>$chmod 777 /Users/yourusername/Desktop/ExtJs_practice/index.html</pre>
說明http://www.hi-docs.com/linux/chmod.html 
如果要關掉nginx,輸入 $nginx -s stop (如果關不掉 , 就輸入 $sudo nginx -s stop)
      
註1 : 看port狀態 和把不要的port 關掉
參考: http://stackoverflow.com/questions/12397175/how-do-i-close-an-open-port-from-the-terminal-on-the-mac
           <pre>$sudo lsof -i:[port_number]</pre> 
           例如 sudo lsof -i:80 (觀看port 80的狀態和PID)
           
           <pre>$sudo kill -15 [port_number的PID]</pre> 
           例如 sudo kill -15 8628 (關掉port 80)

註2 參考 https://coderwall.com/p/dgwwuq/installing-nginx-in-mac-os-x-maverick-with-homebrew 
