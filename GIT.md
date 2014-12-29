*fancy log*

git reflog

*view particular log*

git log HEAD@{5}

*reset to certain point base on above info*

git reset --hard HEAD@{15}

*When doing sth dangerous like --hard reset above, first do...*

git tag BACKUP

*You can return back to it when things go owry with...*

git reset --hard BACKUP

*like reflog with details*

git log -g 
