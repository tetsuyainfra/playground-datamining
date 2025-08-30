

# HOW TO EXEC
```shell
cd dbt-helloworl
mise trust

mise run install
# mise run i
# SEE: mise.toml, task.install


uv add dbt-sqlite

```


# WHAT DID I DO ?
```shell
$mise use python@latest
$mise use uv@latest

$uv init
# reference to .python-version
$vi mise.toml
# python = 3.13
$mise settings --local addidiomatic_version_file_enable_tools = ["python"]

$uv add dbt-core
$uv add dbt-sqlite

$uv run dbt init hello
13:26:06  Running with dbt=1.10.10
13:26:06
Your new dbt project "hello" was created!

For more information on how to configure the profiles.yml file,
please consult the dbt documentation here:

  https://docs.getdbt.com/docs/configure-your-profile

One more thing:

Need help? Don't hesitate to reach out to us via GitHub issues or on Slack:

  https://community.getdbt.com/

Happy modeling!

13:26:06  Setting up your profile.
Which database would you like to use?
[1] sqlite

(Don't see the one you want? https://docs.getdbt.com/docs/available-adapters)

Enter a number: 1  <----- Input
13:26:09  Profile hello written to /home/tetsuyainfra/.dbt/profiles.yml using target's sample configuration. Once updated, you'll be able to start developing with dbt.

$cd hello
$vi ~/.dbt/profiles.yml
~~~
      database: database
      schema: 'main'
      schemas_and_paths:
        #main: '/my_project/data/etl.db' 
        main: '/tmp/etl.db' <-- change other path
        main: 'logs/etl.sqlite' これでプロジェクトのlogsにぶちこめる
~~~
$uv run dbt debug
$ls ./logs/
ok!
```