- Setting Up Alert: 
  
  + docker run --network host -v  /root/alert/default.tmpl:/default.tmpl --name alert-bot metalmatze/alertmanager-bot:0.4.0 --listen.addr=0.0.0.0:8080 --telegram.admin=895016875 --telegram.token=984337884:AAELllXK3LYes75atO725Kl1EdN5LLbnP0U --template.paths=/default.tmpl --alertmanager.url=http://localhost:9093 --bolt.path=/data/bot.db --store=bolt
  
  +  docker run --network host -v /root/alert/alertmanager.yml:/etc/alertmanager/alertmanager.yml -v /root/alert/data:/alertmanager -v /root/alert/default.tmpl:/etc/alertmanager/template/default.tmpl  --name alertmanager prom/alertmanager
  
  +  docker run --network host --name aler-telegram --restart always -e botToken="984337884:AAELllXK3LYes75atO725Kl1EdN5LLbnP0U" -e chatID="1001209086955" jrohy/alertmanager-telegram
  
  + docker run --network host --name alert-telegram --restart always -e botToken="984337884:AAELllXK3LYes75atO725Kl1EdN5LLbnP0U" -e chatID="1001209086955" doctorwhoq/alertbot
  
  + docker run --network host -v /root/alert/alertmanager.yml:/etc/alertmanager/alertmanager.yml -v /root/alert/data:/alertmanager --name alertmanager prom/alertmanager --cluster.peer=192.168.10.155:9094 --cluster.listen-address="0.0.0.0:9094" --config.file="/etc/alertmanager/alertmanager.yml"