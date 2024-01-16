【SSH】
ssh -i ~/.ssh/web-server-hair-station-mika web-server-hair-station-mika@104.198.96.84

【Folder】
scp -i ~/.ssh/web-server-hair-station-mika -r components web-server-hair-station-mika@104.198.96.84:~/src/

【File】
scp -i ~/.ssh/web-server-hair-station-mika components/Footer.tsx web-server-hair-station-mika@104.198.96.84:~/src/components

【Content of default】
server {
    listen 80;
    server_name example.com www.example.com;
    location / {
        proxy_pass http://localhost:8080;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header X-Forwarded-Proto https;
    }
}