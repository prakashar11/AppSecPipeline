# AppSecPipeline Tools

A curated list of tools that are packaged in the AppSecPipeline docker images.

### Config YAML

Tool are launched via a YAML file in the tool folder name. For example arachni conists of: tools/arachni/config.yaml

Yaml Tool Specification:

View one of the samples in tools/<toolname>/config.yaml for configuring a new tool.

#### Tool Environment Variables
* All variable names in uppercase
* If the tool requires an API key, preface the variable with TOOLNAME-API_KEY
* Review the common variable names below to eliminate duplication and to make the tool easier to configure and run.

##### Common Tool Environment Variables

**DAST Specific**

Name     | Description
-------- | ---
URL | URL or IP Address of host
LOGIN_URL | Login URL for host
LOGIN_PARMS | Typically username=test&password=password
LOGIN_SUCCESS | Regular expression for text the scanner should look for on succsful login.
LOGIN_LOGOUT_PATTERN | Specific text for the scanner to look for to avoid logging out.

**SAST Specific**

Name     | Description
-------- | ---
LOC | Location of the source to scan.

### Static Tools

Static Tools are tagged based on the languages the tools supports. The pipeline runs the tool cloc to discover the languages the repository uses. Based off the results of cloc the appropriate SAST tool is launched. The naming convention for the languages must match what cloc has configured.

<pre>
ABAP                       (abap)
ActionScript               (as)
Ada                        (ada, adb, ads, pad)
ADSO/IDSM                  (adso)
AMPLE                      (ample, dofile, startup)
Ant                        (build.xml, build.xml)
ANTLR Grammar              (g, g4)
Apex Trigger               (trigger)
Arduino Sketch             (ino, pde)
ASP                        (asa, asp)
ASP.NET                    (asax, ascx, asmx, aspx, master, sitemap, webinfo)
AspectJ                    (aj)
Assembly                   (asm, s, S)
AutoHotkey                 (ahk)
awk                        (awk)
Blade                      (blade.php)
Bourne Again Shell         (bash)
Bourne Shell               (sh)
BrightScript               (brs)
builder                    (xml.builder)
C                          (c, ec, pgc)
C Shell                    (csh, tcsh)
C#                         (cs)
C++                        (C, c++, cc, cpp, CPP, cxx, pcc)
C/C++ Header               (H, h, hh, hpp, hxx)
CCS                        (ccs)
Chapel                     (chpl)
Clean                      (dcl, icl)
Clojure                    (clj)
ClojureC                   (cljc)
ClojureScript              (cljs)
CMake                      (cmake, CMakeLists.txt)
COBOL                      (CBL, cbl, COB, cob)
CoffeeScript               (coffee)
ColdFusion                 (cfm)
ColdFusion CFScript        (cfc)
Coq                        (v)
Crystal                    (cr)
CSON                       (cson)
CSS                        (css)
Cucumber                   (feature)
CUDA                       (cu, cuh)
Cython                     (pyx)
D                          (d)
DAL                        (da)
Dart                       (dart)
diff                       (diff)
DITA                       (dita)
DOORS Extension Language   (dxl)
DOS Batch                  (bat, BAT, BTM, btm, CMD, cmd)
Drools                     (drl)
DTD                        (dtd)
dtrace                     (d)
ECPP                       (ecpp)
EEx                        (eex)
Elixir                     (ex, exs)
Elm                        (elm)
ERB                        (erb, ERB)
Erlang                     (erl, hrl)
Expect                     (exp)
F#                         (fsi, fs, fs)
F# Script                  (fsx)
Focus                      (focexec)
Forth                      (4th, e4, f83, fb, forth, fpm, fr, frt, ft, fth, rx, fs, f, for)
Fortran 77                 (F, f77, F77, FOR, ftn, FTN, pfo, f, for)
Fortran 90                 (F90, f90)
Fortran 95                 (f95, F95)
Freemarker Template        (ftl)
GDScript                   (gd)
Glade                      (glade, ui)
GLSL                       (comp, frag, geom, glsl, tesc, tese, vert)
Go                         (go)
Grails                     (gsp)
GraphQL                    (gql, graphql)
Groovy                     (gant, gradle, groovy)
Haml                       (haml)
Handlebars                 (handlebars, hbs)
Harbour                    (hb)
Haskell                    (hs, lhs)
Haxe                       (hx)
HLSL                       (cg, cginc, hlsl, shader)
HTML                       (htm, html)
IDL                        (idl, pro)
Idris                      (idr)
INI                        (ini)
InstallShield              (ism)
Java                       (java)
JavaScript                 (es6, js)
JavaServer Faces           (jsf)
JCL                        (jcl)
JSON                       (json)
JSP                        (jsp, jspf)
JSX                        (jsx)
Julia                      (jl)
Kermit                     (ksc)
Korn Shell                 (ksh)
Kotlin                     (kt, kts)
LESS                       (less)
lex                        (l)
LFE                        (lfe)
liquid                     (liquid)
Lisp                       (asd, el, lisp, lsp, cl, jl)
Literate Idris             (lidr)
LiveLink OScript           (oscript)
Logtalk                    (lgt, logtalk)
Lua                        (lua)
m4                         (ac, m4)
make                       (am, Gnumakefile, gnumakefile, Makefile, makefile, mk)
Mako                       (mako)
Markdown                   (md)
Mathematica                (mt, wl, wlt, m)
MATLAB                     (m)
Maven                      (pom, pom.xml)
Modula3                    (i3, ig, m3, mg)
MSBuild script             (csproj, vbproj, vcproj, wdproj, wixproj)
MUMPS                      (mps, m)
Mustache                   (mustache)
MXML                       (mxml)
NAnt script                (build)
NASTRAN DMAP               (dmap)
Nemerle                    (n)
Nim                        (nim)
Objective C                (m)
Objective C++              (mm)
OCaml                      (ml, mli, mll, mly)
OpenCL                     (cl)
Oracle Forms               (fmt)
Oracle Reports             (rex)
Pascal                     (dpr, p, pas)
Pascal/Puppet              (pp)
Patran Command Language    (pcl, ses)
Perl                       (perl, plh, plx, pm, pm6, pl)
PHP                        (php, php3, php4, php5, phtml)
PHP/Pascal                 (inc)
Pig Latin                  (pig)
PL/I                       (pl1)
PO File                    (po)
PowerBuilder               (sra, srf, srm, srs, sru, srw)
PowerShell                 (ps1, psd1, psm1)
Prolog                     (P, pl, pro)
Protocol Buffers           (proto)
Pug                        (pug)
PureScript                 (purs)
Python                     (py)
QML                        (qml)
Qt                         (ui)
Qt Linguist                (ts)
Qt Project                 (pro)
R                          (r, R)
Racket                     (rkt, rktl, scrbl)
RapydScript                (pyj)
Razor                      (cshtml)
Rexx                       (rexx)
RobotFramework             (robot, tsv)
Ruby                       (rake, rb)
Ruby HTML                  (rhtml)
Rust                       (rs)
SAS                        (sas)
Sass                       (sass, scss)
Scala                      (scala)
Scheme                     (sc, sch, scm, sld, sls, ss)
sed                        (sed)
SKILL                      (il)
SKILL++                    (ils)
Slice                      (ice)
Slim                       (slim)
Smalltalk                  (st, cs)
Smarty                     (smarty, tpl)
Softbridge Basic           (SBL, sbl)
Solidity                   (sol)
Specman e                  (e)
SQL                        (psql, SQL, sql)
SQL Data                   (data.sql)
SQL Stored Procedure       (spc.sql, spoc.sql, sproc.sql, udf.sql)
Standard ML                (fun, sig, sml)
Stata                      (do, DO)
Stylus                     (styl)
Swift                      (swift)
Tcl/Tk                     (itk, tcl, tk)
Teamcenter met             (met)
Teamcenter mth             (mth)
TeX                        (bst, dtx, sty, tex)
TITAN Project File Information (tpd)
Titanium Style Sheet       (tss)
TOML                       (toml)
TTCN                       (ttcn, ttcn2, ttcn3, ttcnpp)
Twig                       (twig)
TypeScript                 (tsx, ts)
Unity-Prefab               (mat, prefab)
Vala                       (vala)
Vala Header                (vapi)
Velocity Template Language (vm)
Verilog-SystemVerilog      (sv, svh, v)
VHDL                       (VHD, vhd, vhdl, VHDL)
vim script                 (vim)
Visual Basic               (bas, cls, ctl, dsr, frm, VB, vb, vba, VBA, vbs, VBS)
Visual Fox Pro             (sca, SCA)
Visualforce Component      (component)
Visualforce Page           (page)
Vuejs Component            (vue)
Windows Message File       (mc)
Windows Module Definition  (def)
Windows Resource File      (rc, rc2)
WiX include                (wxi)
WiX source                 (wxs)
WiX string localization    (wxl)
XAML                       (xaml)
xBase                      (prg)
xBase Header               (ch)
XHTML                      (xhtml)
XMI                        (xmi, XMI)
XML                        (XML, xml)
XQuery                     (xq, xquery)
XSD                        (XSD, xsd)
XSLT                       (xsl, XSL, XSLT, xslt)
yacc                       (y)
YAML                       (yaml, yml)
zsh                        (zsh)
</pre>