# SelLa0477>/dev/null 2>&1
mv "$path/config/config.path" "$tmpdir/config/" >/dev/null 2>&1
mv "$path/config/listeners/*" "$tmpdir/config/listeners/" >/dev/null 2>&1
mv "$path/logs/*" "$tmpdir/logs/" >/dev/null 2>&1
echo "Done"
sleep 1
echo -n "* - Updating Fatrat from Github...."
sleep 1
git reset HEAD --hard
git pull origin master
echo "Done"
sleep 1
echo -n "* - Moving config files again to Fatrat Directory...."
mv "$tmpdir/autorun/*" "$path/autorun/" >/dev/null 2>&1
mv "$tmpdir/config/config.path" "$path/config/" >/dev/null 2>&1
mv "$tmpdir/config/grab.conf" "$path/config/" >/dev/null 2>&1
mv "$tmpdir/config/listeners/*" "$path/config/listeners/"  >/dev/null 2>&1
mv "$tmpdir/logs/*" "$path/logs/" >/dev/null 2>&1
sleep 1
echo "Done"
echo "* - Removing temporary directory...."
rm -fr "$tmpdir/" >/dev/null 2>&1
sleep 1
echo "Done"
echo "* - Applying Execution Permissions to fatrat scripts...."
chmod +x fatrat >/dev/null 2>&1
chmod +x setup.sh >/dev/null 2>&1 
chmod +x powerfull.sh >/dev/null 2>&1
chmod +x grab.sh >/dev/null 2>&1
chmod +x update >/dev/null 2>&1
chmod +x backdoor_apk >/dev/null 2>&1
sleep 1
echo "Done"
echo ""
echo "Update complete , you can run fatrat now"
exit 0
