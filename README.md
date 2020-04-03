npm i -g plugman

plugman create --name datepickercordovaplugin --plugin_id com.kuldeep.datepickercordovaplugin --plugin_version 1.0.0
plugman createpackagejson .\datepickercordovaplugin\
cd .\datepickercordovaplugin\
plugman platform add --platform_name android
cd ..

cordova create datepicker com.datepicker datepickerapp
cd .\datepicker\
cordova platform add android
plugman install --platform android --project platforms/android --plugin "..\datepickercordovaplugin\"
plugman install --platform android --project platforms/android --plugin "..\datepickercordovaplugin" --save
cordova serve android