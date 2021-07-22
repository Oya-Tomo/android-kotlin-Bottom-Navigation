# android-kotlin-Bottom-Navigation
#ボトムナビゲーションのやり方

１．概要
　このコードはボトムナビゲーションによってMainActivityのFragmentを切り替え、画面遷移をするコードです。
activity_main.xmlに配置してあるNavHostFragmentがFragmentを格納するウィジェットで、このなかのFragmentを切り替えることによって画面が切り替わります。
NavHostFragment内のFragmentを切り替えるためにはNavHostFragmentが持つNavigationControllerを取得し、それを使ってNavigation()してあげる必要があります。
MainActivity.ktでは、BottomNavigationViewをNavigationControllerに紐づけて自動的にNavigation()させています。

２．手順
・Fragmentの追加（自分の使いたいFragmentを用意する　※この時、あまり多すぎるとBottomNavigationViewに収まらない可能性があるのでその点も考慮する）
・NavigationGraph.xmlの追加
　<res(Project Tree)>　→　<New>　→　<Android Resource File>　→　<Navigation>
　NavigationGraphを開き、Fragmentを追加する。
・MenuFile.xmlの追加
　android:id にはNavigationGraph.xmlで追加したFragmentのIdを登録する。
　android:titleにはBottomNavigationViewに表示されるタイトルを決める。
 
　※BottomNavigationViewに追加するファイルです。
・MainActivity.ktにてNavHostFragmentのNavControllerを取得
・BottomNavigationViewを取得
・BottomNavigationView.setupWithNavController(さっき取得したNavController)で紐づけ。
