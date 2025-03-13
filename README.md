# linux

echo baf08f87d26c48afe9c0a03a06cce4900711f9d7320380aee95efc0342abe5a1> secret-file & curl.exe -sO http://localhost:8080/jnlpJars/agent.jar & java -jar agent.jar -url http://localhost:8080/ -secret @secret-file -name "dhruv_win" -webSocket -workDir "C:\jenkins"
