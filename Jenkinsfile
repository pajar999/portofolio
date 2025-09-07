pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/pajar999/portofolio.git'
            }
        }

        stage('Build') {
            steps {
                echo '✅ Build step - static website jadi cuma cek file'
                sh 'ls -lah'
            }
        }

        stage('Deploy') {
            steps {
                echo '🚀 Deploy ke Nginx folder...'
                // Hapus semua isi lama lalu copy file baru
                sh 'rsync -av --delete ./ /root/lab-docker/website/'
            }
        }
    }

    post {
        success {
            echo '🎉 Deployment sukses!'
        }
        failure {
            echo '❌ Deployment gagal!'
        }
    }
}
