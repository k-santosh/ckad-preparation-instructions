# My CKAD Preparation Journey
About myself, I am Santosh Kumar and have experience of working with Kubernetes more than two years. So, Overall I had an intermediate level of experience. 

# Exam Registration 
If your company is going to reimburse the certification Cost, then you can buy at any time. However if you are going to get it done from your own pocket. Better to wait for **Black Friday** or **Christmas** you will get very good discount. Example: Generally the certification cost is around $315, whereas during the offer you can get it up to $180. The registrations are valid for a Year. So within the year you can attempt any time. 

# Exam syllabus
[CKAD_Curriculum](https://github.com/cncf/curriculum/blob/master/CKAD_Curriculum_v1.22.pdf)

# Preparation 
- Mumshad course on Udemy is very good. It has practice set on kodekloud, which gives enough practice materials. 
- Lighting Lab is similar to Exam questions. If you are able to solve the lighting lab within 45 min with 80% . You are well ready for exams.

# Practice set
- [CKAD Exercise](https://github.com/dgkanatsios/CKAD-exercises)
- [CKAD Practice Sets](https://codeburst.io/kubernetes-ckad-weekly-challenges-overview-and-tips-7282b36a2681)

# Exams minor tips. 
- Use the alias, this will take around 1-2 min for you. 
```
alias k='kubectl'
alias kf='kubectl --force'
alias kn='kubectl -n $ns'
alias kdry='kubectl --dry-run=client -o yaml'
alias kdnry='kubectl -n $ns --dry-run=client -o yaml'
```
Now, when a questions is specific to a particular namespace set ns=<namespace>,  and now use alias kn/kndry instead of k/dry. This way you don't have to change the default namespace in the kubeconfig file. 

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
sys	0m0.048s
```
```
ubuntu@utility-node:~$ time kf delete pod busybox
warning: Immediate deletion does not wait for confirmation that the running resource has been terminated. The resource may continue to run on the cluster indefinitely.
pod "busybox" force deleted

real	0m0.194s
user	0m0.116s
sys	0m0.024s
```

# Some Others tips
- Use below command to execute a busybox pod for debugging purpose. **--rm** option will delete the pods once you will exit.
```
k run --rm -it busybox --image=busybox --image-pull-policy=IfNotPresent --
```

# Terminals shortcut
- `ctrl+A` to jump to start of the line
- `ctrl+E` to jump to end of the line
- `ctrl+K` to kill the line starting from the cursor position
- `ctrl+W` to remove the word backwards from cursor position
- `CTRL-LEFT` Move left one word.
- `CTRL-RIGHT` Move right one word.

# Vi Shortcuts
- `Shift + G`: Move to end of the file
- `|` : Positions cursor at beginning of line
- `$` : Positions cursor at end of line
- `u` : undo last command
- `W` : Positions cursor to the next word
- `B` : Positions cursor to previous word
- `:set number` : To set number
- `/string` : Search a string in the file
- `:s/pattern/replace/` : Replace in the same line
- `:%s/pattern/replace/` :  Replace all occurrence in the file
## Deletion Shortcuts
- `dd`: delete line
- `dG`: delete till end of file
- `d$`: Delete till end of line
- `d|`: Delete till beginning of line
- `:n` : Moves to nth line  
