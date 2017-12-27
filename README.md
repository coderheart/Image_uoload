# Image_uoload

 if($_FILES['file_upload1']['tmp_name']==""){ 
            $f_insnt1=""; 
            }
            else{
              
              $tmp_file1 = $_FILES['file_upload1']['tmp_name'];
              $target_file1 = basename($_FILES['file_upload1']['name']);
              $upload_dir1 = "../uploads";
              $file_typ1 = basename($_FILES['file_upload1']['type']);
              $cur_file1=$upload_dir1."/".$target_file1;
              if($target_file1==""){ $f_insnt1="";} else{
              $ran=rand(10000,999999);
              $f_insnt1="admin-$ran.".$file_typ1;
              $rename_file1=$upload_dir1."/admin-$ran.".$file_typ1;
              
              if(move_uploaded_file($tmp_file1, $upload_dir1."/".$target_file1)) {
              rename("$cur_file1", "$rename_file1");} 
              else {
              $error = $_FILES['file_upload1']['error'];
              $message = $upload_errors[$error];}
              }
          }
