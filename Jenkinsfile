pipeline {
    agent any
    stages{
        stage('clone the repo and removing the existing one')
        {
          steps {
              sh "sudo rm -rf /home/suparuek/project"
              sh "cd /home/suparuek/"
              sh "mkdir -p /home/suparuek/project"
              sh "cd /home/suparuek/project"
              sh "git clone https://github.com/supiwmi/ITS.git /home/suparuek/project"
               
               }
         }
         
         stage("copying files to /var/www/html")
         {
           steps 
           {
              sh "sudo cp /home/suparuek/project/www/html/index.html /var/www/html/"
           }
          }
          
           stage("Installing the webserver and starting its service")
          {
            steps
            {
              sh "sudo apt install apache2 -y"
              sh "sudo systemctl start apache2"
            }
          }
          
          
          stage("Restarting the apache2 service")
          {
            steps
            {
              sh "sudo systemctl restart apache2"
            }
          }
               
    }

}
