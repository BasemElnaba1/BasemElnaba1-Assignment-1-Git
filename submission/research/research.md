# Research


Git Command Research

البحث ده بيشرح شوية أوامر مهمة في Git وكل أمر بيعمل إيه وإمتى ممكن أستخدمه في مشروع حقيقي 

1. Git Squash

الـ Git Squash معناه إني أدمج كذا commit صغيرة في commit واحدة. الفكرة منه إن الـ Git history يبقى أنضف وأسهل لأي حد يراجعه بعد كده

وأنا شغال على feature جديدة طبيعي أعمل commits كتير، زي تعديل صغير أو إصلاح bug أو تغيير اسم حاجة قبل ما أدمج الـ feature مع الفرع الأساسي، ممكن أجمع الـ commits دي في commit واحدة واضحة

مثال:

git rebase -i HEAD~3

سيناريو عملي

لو أنا شغال على صفحة Login وعملت commits زي:

Add login page
Fix login button
Fix validation

ممكن أدمجهم كلهم في commit واحدة اسمها:

Create login page

وده بيخلي تاريخ المشروع مرتب وواضح أكتر 

2. Git Merge vs Git Rebase

الـ git merge والـ git rebase الاتنين بنستخدمهم علشان نتعامل مع شغل موجود في branches مختلفة، بس كل واحد فيهم بيعمل ده بطريقة مختلفة.

Git Merge

git merge بيجمع تغييرات branch مع branch تاني، وبيسيب تاريخ الشغل زي ما حصل بالظبط.

مثال:

git checkout main
git merge feature

لو عندنا:

main:       A --- B --- C
                  \
feature:           D --- E

بعد الـ merge ممكن التاريخ يبقى:

A --- B --- C ------- M
       \             /
        D --------- E

الـ M هنا هي Merge Commit 

الميزة في merge إنه بيحافظ على شكل وتاريخ الفروع زي ما حصلوا فعلًا 

Git Rebase

git rebase بياخد commits بتاعة branch ويحطها بعد آخر commit في branch تاني.

مثال:

git checkout feature
git rebase main

قبل:

A --- B --- C
       \
        D --- E

بعد:

A --- B --- C --- D' --- E'

الميزة الأساسية في rebase إنه بيخلي الـ Git history مستقيم وأنضف 

سيناريو عملي

لو أنا شغال على feature branch وفي نفس الوقت باقي الفريق نزلوا commits جديدة على main، ممكن أستخدم rebase علشان أحدث الفرع بتاعي وأحط شغلي بعد آخر نسخة من main

أما لو عايز أحافظ على تاريخ الفروع زي ما حصل بالظبط، أستخدم merge 

3. Git Help

git help بنستخدمه لما نكون عايزين نعرف تفاصيل أكتر عن أي Git command، زي طريقة استخدامه والـ options المتاحة فيه.

مثال:

git help commit

وممكن كمان:

git commit --help

سيناريو عملي

لو نسيت option معين في git commit أو git log، بدل ما أروح أدور على الإنترنت، ممكن أستخدم git help وأشوف التفاصيل بسرعة.
