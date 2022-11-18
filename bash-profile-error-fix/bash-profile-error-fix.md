# bash profile error fix

error အကျဉ်း

\--------------------

ဖြစ်တဲ့ error ကတော့ bash profile error လို့ ယူဆရပါတယ်

bash ပေါ်မှာ run နေတဲ့ process တစ်ခုခုက end မသွားပဲ ham နေတာမျိုး ရပ်နေတာမျိုးအနေအထား မှာ စိတ်ပိတ်သွားတာမျိုး ပါဝါ down သွားတာမျိုးမှာ ဖြစ်တတ်ပါတယ် user က login ဝင်တဲ့အချိန်မှာ bash shell ကို ခေါ်မသုံးနိုင်တော့တာပါ minimal မှာဆို Login ဝင်ပြီးတာနဲ့ ဘာမှမပေါ် တော့တာမျိုးဖြစ်တတ်ပါတယ်

troubleshooting step 01

\---------------------------------

အရင်ဆုံး ဘာဖြစ်လဲဆိုတာ troubleshooting လုပ်ဖို့ အတွက် shell တစ်ခုခု ကိုဖွင့် ကြည့်မှာပါ Linux OS တော်တော်များများမှာ os installation လုပ်ပြီးတာနဲ့ default အနေနဲ့ sh shell နဲ့ bash shell ကတော့ ပါလာပြီးသားပါ

cat command နဲ့ /etc/shells ဆို တဲ့ ဖိုင်လေးကို ကြည့်ကြည့်ရင်သိနိုင်ပါတယ် bash shell မရဘူးဆိုတော့ sh shell ကို ဝင်ကြည့်မှာပါ ။ အဲ့တော့ ဘာမှ လုပ်လို့မရတဲ့ အခြေ အနေမှာ sh shell ကို ဝင်ဖို့ အတွက် အလွယ်တစ်ကူသုံးလို့ရတဲ့ terminal တစ်ခုကိုသုံးလိုက်ပါတယ် xterm ဆိုတဲ့ကောင်လေးပါ အဲ့တာလေးကို gui app store ကနေ down လိုက်ပါတယ် ပြီးရင်တော့ alt+f2 ကိုနှိပ်လိုက်ပါတယ် (alt+f2 ကတော့ windows မှာဆိုရင် Windows key + R နှိပ်ပြီး ခေါ်တဲ့ run box လိုပါပဲ linux မှာတော့ Command Box လိုလည်း ခေါ်ကြပါတယ်) alt+f2 နှိပ်ပြီးလို့ command box ကျလာတဲ့အချိန်မှာ xterm -e sh ဆိုပြီး ရိုက်ထည့်လိုက်ရင် xterm terminal ဟာ sh shell နဲ့ ပွင့် လာပါတယ် အဲ့ ဒီမှာ root access ရအောင်လုပ်ပြီးတော့ root အကောင့်နဲ့ ဝင် လိုက်တော့ bash shell က root အကောင့် မှာ ကောင်းကောင်းအလုပ်လုပ်ပါတယ် နောက် user တစ်ယောက် add ကြည့်တော့လည်း bash shell က ကောင်းကောင်းအလုပ်လုပ်ပါတယ် အဲ့တာ ဆို user ရဲ့ default bash shell profile error ဖြစ်တာ သေချာသလောက်ရှိသွားပြီ အဲ့ user ကို usermod -s /bin/sh username နဲ့ default sh shell သတ်မှတ်ပြီး log out > log in ပြန်လုပ်ကြည့်တော့ sh shell နဲ့ terminal က ပြန်ပွင့် လာပါပြီ

troubleshooting step 02

\---------------------------------

ဒါဆိုရင်တော့ အမြန်ဆုံး နည်း ကတော့ error တစ်ခု ချင်းလိုက် မရှာတော့ ပဲ user ရဲ့ bash profile ကို ပြန်ပြီး restore လုပ်နိုင်ပါတယ်။ ဘယ်ကနေ restore လုပ်မလဲဆိုတော့ /etc/skel/ ဆိုတဲ့ folder ထဲကပါ။ ( ကျွန်တော်တို့တွေက user အကောင့်တစ်ခုခု ကို adduser command နဲ့ add လိုက်တဲ့အချိန်မှာ နောက်ကွယ်မှာ လုပ်ဆောင်ချက်တချို့ကိုတစ်ပြိုင်ထဲ လုပ်သွားပါတယ် အဲ့ထဲမှာ /home/ directory အောက်မှာ user profiles တွေ ဆောက်မယ် user profile ထဲမှာပဲ - ဥပမာ အားဖြင့် gui ဆိုရင် Desktop တို့ Download အစရှိသည် တို့အပြင် တခြား လိုအပ်တဲ့ ဖိုင်တွေကိုဆောက်သွားပါတယ် အဲ့ထဲမှာ သေချာပေါက်ပါသွားမှာကတော့ shell profile တွေပဲဖြစ်ပါတယ်။ shell profile တွေကိုတော့ /etc/skel/ အောက်ကနေ copy ကူးထည့်လိုက်ပါတယ်) ls -a /etc/skel/ နဲ့ ကြည့်လိုက်မယ်ဆိုရင် default အားဖြင့် > .bash\_logout .bash\_profile .bashrc ဒီဖိုင်လေးသုံးဖိုင်ကိုတွေ့ရမှာပါ zsh shell install လုပ်ပြီးသားဆိုရင်တော့ .zshrc ကိုပါတွေ့ရမှာပါ ဆိုတော့ /etc/skel/ အောက်က ဖိုင်တွေအားလုံး ကို /home/username/ အောက်ကို copy ကူး ပြီး replace လုပ်လိုက်ရင် အဆင်ပြေသွားပါပြီ ။ ဒါတွေအားလုံးကို command မရလည်း gui နဲ့ လုပ်လို့ရပါတယ် root access ရှိနေဖို့တော့လိုပါတယ်

Keypoint\
\----------

Bash profile error

cp /etc/skel/\* /home/username/

OK
