# reproducer-rector-7240

For https://github.com/rectorphp/rector/issues/7240

When executing `make refactoring` via rector, it should also update the `EnumCommand.php` file ❗

Missing diff:
```diff
diff --git a/src/Command/EnumCommand.php b/src/Command/EnumCommand.php
index 1dc9e87..bdeae08 100644
--- a/src/Command/EnumCommand.php
+++ b/src/Command/EnumCommand.php
@@ -19,8 +19,8 @@ final class EnumCommand extends Command
     {
         $io = new SymfonyStyle($input, $output);

-        $io->text(get_class(Gender::MALE()));
-        $io->text(Gender::MALE()->getValue());
+        $io->text(get_class(Gender::MALE));
+        $io->text(Gender::MALE->value);

         return Command::SUCCESS;
     }
```
