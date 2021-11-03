# My CKAD Preparation Journey
About myself, I am Santosh Kumar and have experience of working with Kubernete more than two years. So, Overall I had an intermediate level of experience. 

# Exam Registration 
If your company is going to reimbuse the certification Cost, then you can buy at anytime. However if you are going to get it done from your own pocket. Better to wait for **Black Friday** or **Christmas** you will get very good discount. Example: Generally the certification cost is around $315, where as during the offer you can get it up to $180. The registrations are valid for a Year. So within the year you can attempt any time. 

# Exam syllabus
[CKAD_Curriculum] (https://github.com/cncf/curriculum/blob/master/CKAD_Curriculum_v1.22.pdf)

# Preparation 
- Mumshad course on Udemy is very good. It has practice set on kodekloud, which gives enough practice materials. 
- Lighting Lab is similar to Exam questions. If you are able to solve the lighting lab within 45 min with 80% . You are well ready for exams.

# Practice set
- CKAD Excercise: https://github.com/dgkanatsios/CKAD-exercises
- CKAD questions and answers: https://codeburst.io/kubernetes-ckad-weekly-challenges-overview-and-tips-7282b36a2681

# Exams minor tips. 
- Use the alias, this will take around 1-2 min for you. 
```
alias k='kubectl'
alias kf='kubectl --force'
alias kn='kubectl -n $ns'
alias kdry='kubectl --dry-run=client -o yaml'
alias kdnry='kubectl -n $ns --dry-run=client -o yaml'
```
Now, when a questions is specifc to a particular namespace set ns=<namespace>,  and now use alias kn/kndry instead of k/dry. This way you don't have to change the default namespace in the kubeconfig file. 

- To use autocompletion feature you will have to add below entry to bashrc file. 
```
source <(kubectl completion bash)
complete -F __start_kubectl k
complete -F __start_kubectl kf
complete -F __start_kubectl kn
complete -F __start_kubectl kdry
complete -F __start_kubectl kdnry
```
- Also create a vimrc file with below content. 
```
set ts=2
set sts=2
set sw=2
set et
set autoindent
```

- Use **--force*** command it will save you around 30sec for each commands. 
```
ubuntu@utility-node:~$ time k delete pod busybox
pod "busybox" deleted

real	0m38.732s
user	0m0.084s
sys	    0m0.048s
```
```
ubuntu@utility-node:~$ time kf delete pod busybox
warning: Immediate deletion does not wait for confirmation that the running resource has been terminated. The resource may continue to run on the cluster indefinitely.
pod "busybox" force deleted

real	0m0.194s
user	0m0.116s
sys	    0m0.024s
```