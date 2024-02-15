{{- .Scratch.Set "basedir" "files/" -}}
{{- .Scratch.Set "path" (.Get 0) -}}
{{- if hasPrefix (.Scratch.Get "path") "/" -}}
  {{- .Scratch.Set "path" (slicestr (.Scratch.Get "path") 1) -}}
{{- end -}}
{{- .Scratch.Add "basedir" (.Scratch.Get "path") -}}
{{- .Scratch.Get "basedir" | absLangURL -}}
