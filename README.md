# linux

echo baf08f87d26c48afe9c0a03a06cce4900711f9d7320380aee95efc0342abe5a1> secret-file & curl.exe -sO http://localhost:8080/jnlpJars/agent.jar & java -jar agent.jar -url http://localhost:8080/ -secret @secret-file -name "dhruv_win" -webSocket -workDir "C:\jenkins"




java -jar agent.jar -jnlpUrl http://<jenkins-master-url>:8080/computer/<agent-name>/slave-agent.jnlp -secret <secret-key> -workDir "<agent-work-dir>"


java -jar agent.jar -jnlpUrl http://localhost:8080/computer/dhruv_win/slave-agent.jnlp -secret baf08f87d26c48afe9c0a03a06cce4900711f9d7320380aee95efc0342abe5a1 -name "dhruv_win" -workDir "C:\jenkins"

java -jar agent.jar -jnlpUrl file:///C:/jenkins/slave-agent.jnlp -secret baf08f87d26c48afe9c0a03a06cce4900711f9d7320380aee95efc0342abe5a1 -workDir "C:\jenkins"




echo baf08f87d26c48afe9c0a03a06cce4900711f9d7320380aee95efc0342abe5a1> secret-file
curl.exe -sO http://192.168.0.113:8080/jnlpJars/agent.jar
java -jar C:\jenkins\agent.jar -url http://192.168.0.113:8080/ -secret @secret-file -name "dhruv_win" -webSocket -workDir "C:\jenkins"


curl.exe -sO http://192.168.0.113:8080/jnlpJars/agent.jar
java -jar C:\jenkins\agent.jar -url http://192.168.0.113:8080/ -secret baf08f87d26c48afe9c0a03a06cce4900711f9d7320380aee95efc0342abe5a1 -name "dhruv_win" -webSocket -workDir "C:\jenkins"
