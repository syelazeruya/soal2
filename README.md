## Revisi
Kendala yang terjadi saat demo adalah tidak bisa menampilkan menu admin, sehingga diperlukan revisi untuk memperbaiki kode pada skrip login.sh
Kesalahan sebelumnya terjadi karena kesalahan saat menuliskan fungsi yang seharusnya 'admin_menu', namun yang tertulis adalah 'admin_actions'.
<pre>
  check_credentials "$email" "$password"
        if [ $? -eq 0 ]; then
            echo "[ $(date +'%d/%m/%Y %H:%M:%S') ] [LOGIN SUCCESS] U>

            is_admin=$(grep "^$email:" users.txt | cut -d: -f6)
            if [ "$is_admin" == "admin" ]; then
                admin_menu #Bagian yang diubah, sebelumnya adalah admin_actions
            else
                echo "Login successful!"
                echo "You don't have admin privileges. Welcome!"
            fi
        else
            echo "[ $(date +'%d/%m/%Y %H:%M:%S') ] [LOGIN FAILED] ER>
            echo "ERROR: Incorrect password."
            read -p "Forgot Password? (y/n): " choice
            if [ "$choice" == "y" ]; then
                forgot_password "$email"
            fi
        fi
        ;;
</pre>


## Dokumentasi
![dokumentasi ](https://github.com/syelazeruya/soal2/assets/151950309/da40a214-8100-4b05-986f-a2683752bc05)
