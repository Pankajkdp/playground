# playground

What it offers/solves
Give control to authors for creating page structure
maintain live connection with page
Reduces variations of page components and promoting a generic page component
reduce multiple versions of component configurations and settings and promoting resuability

template>structure defines structure of the page by organizing components. components can't be moved or deleted from the page. template can have locked and editable components(which author can edit, have ditable property on node).

template>intitial setup initial content for the page, only editable componenets can be edited in initial mode.

template>policy only stores references to actual policy which is stored under wcm/polices

template>layout for defining layout for locked and editable components both

unlocking a component will move its content from structure to initial

The out-of-the box template types are stored under:
/libs/settings/wcm/template-types

Your site-specific template types should be stored in the comparable location of:
/apps/settings/wcm/template-types

Template types and policies are inherited across all folders according to the following order of precedence:
The current folder.
Parent(s) of the current folder.
/conf/global
/apps
/libs
A list of all allowed entries is created. If any configurations overlap (path/label), only the instance closest to the current folder is presented to the user.
When creating templates you should consider:

The impact of changes to the template once pages have been created from that template.

Here is a list of the different operations possible on templates together with how they affect the pages created from them:

Changes to the structure:
 These are immediately applied to the resulting pages.
Changes to content policies and design configurations:
 These apply immediately to the resultant pages. 
Changes to the initial content:
 These only apply to pages created after the changes to the template.
Changes to the layout depend on whether the modified component is part of:
 Structure-only - applied immediately
 Contain initial content - only on pages created after the change
Take special caution when:
 Locking or unlocking components on enabled templates.
 This can have side-effects, as existing pages can already be using it. Typically:
 Unlocking components (that were locked) will be missing on existing pages.
 Locking components (that were editable) will hide that content from being displayed on the pages.
 
 - include cq.shared clientlib in page componenet/templateType
- other than admin, template-authors group has privileges to create/edit templates
- templateType defines
	- resourceType for page component
	- policy for the root node, which componentns are alolowed in template editor
	- breakpoints for responsive grid and mobile emulator
Never enter any information that needs to be internationalized into a template.

CF

Adobe Experience Manager (AEM) Content Fragments allow you to design, create, curate and use page-independent content which can be used in multiple locations/over multiple channels.

Constituent Parts of a Content Fragment
- Fragment Elements
- Fragment Metadata
- Master
- Variations
- Fragment Paragraph
- Inserted Asset
- Associated Content
- Fragment Template
- Fragment component

Saving Fragment Changes
Save also updates any references and ensures that the dispatcher is flushed as required. These changes can take time to process. Due to this, there can be a performance impact on a large/complex/heavily-loaded system.

Please bear this in mind when using Save and then quickly re-entering the fragment editor to make and save further changes.

While editing your content fragment AEM automatically creates versions to ensure that prior content can be restored if you Cancel your changes:

When a content fragment is opened for editing AEM checks for the existence of the cookie-based token that indicates whether an editing session exists:
- If the token is found, the fragment is considered to be part of the existing editing session.
- If the token is not available and the user starts editing content, a version is created and a token for this new editing session is sent to the client, where it is saved in a cookie.
- While there is an active editing session, the content being edited is automatically saved every 600 seconds (default).
Default value, see:
/libs/settings/dam/cfm/jcr:content/autoSaveInterval
- If the user selects to Cancel the edit, the version created at the start of the editing session is restored and the token is removed to end the editing session.
- If the user selects to Save the edits, the updated elements/variations are persisted and the token is removed to end the editing session.

Can add Assets to content fragments
If, after adding an asset, you change format to:
Plain Text: the asset will be completely lost from the fragment.
Markdown: the asset will not be visible, but will still be there when you return to Rich Text.

Markdown format allows to create content quickly using markdown syntax

Variations Mode:
- Create/update/delete/rename a variation
- Synchronize
- Summarize
