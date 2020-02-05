<h1>hosts修改工具</h1>
    title  雨苁 www.ddosi.com    QQ569743  别认输,因为没人希望你赢
    @echo off
    mode con lines=100 cols=90
    %1 mshta vbscript:CreateObject("Shell.Application").ShellExecute("cmd.exe","/c %~s0 ::","","runas",1)(window.close)&&exit
    cd /d "%~dp0"
    :main
    cls
    echo ------------------------------------------------------------
    echo                Metasploit : 打死你个龟孙 ! 
    echo ------------------------------------------------------------
    echo                          ########                  #
    echo                      #################            #
    echo                   ######################         #
    echo                  #########################      #
    echo                ############################
    echo               ##############################
    echo               ###############################
    echo              ###############################
    echo              ##############################
    echo                              #    ########   #
    echo                 ##        ###        ####   ##
    echo                                      ###   ###
    echo                                    ####   ###
    echo               ####          ##########   ####
    echo               #######################   ####
    echo                 ####################   ####
    echo                  ##################  ####
    echo                    ############      ##
    echo                       ########        ###
    echo                      #########        #####
    echo                    ############      ######
    echo                   ########      #########
    echo                     #####       ########
    echo                       ###       #########
    echo                      ######    ############
    echo                     #######################
    echo                     #   #   ###  #   #   ##
    echo                     ########################
    echo                      ##     ##   ##     ##
    echo -----------------------------------------------------------
    echo    雨苁     QQ569743     www.ddosi.com    cpu@usa.com                 
    color 0a
    echo.-----------------------------------------------------------
    echo.
    echo.                     输入1回车两次                        
    echo.
    echo.-----------------------------------------------------------
    
    if exist "%SystemRoot%\System32\choice.exe" goto Win7Choice
    
    set /p choice=请输入数字并按回车键确认:
    
    echo.
    if %choice%==1 goto host DNS
    if %choice%==2 goto CL
    cls
    "set choice="
    echo 您输入有误，请重新选择。
    ping 127.0.1 -n "2">nul
    goto main
    
    :Win7Choice
    choice /c 12 /n /m "请输入相应数字："
    if errorlevel 2 goto CL
    if errorlevel 1 goto host DNS
    cls
    goto main
    
    :host DNS
    cls
    color 0a
    copy /y "hosts" "%SystemRoot%\System32\drivers\etc\hosts"
    ipconfig /flushdns
    
    goto end
    
    :CL
    cls
    color 0a
    @echo 127.0.0.1 localhost > %SystemRoot%\System32\drivers\etc\hosts
    echo hosts已恢复.
    echo.
    goto end
    
    :end
    echo 请按任意键退出.
    @Pause>nul
