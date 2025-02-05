## API Report File for "@backstage/plugin-techdocs"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts
/// <reference types="react" />

import { ApiRef } from '@backstage/core-plugin-api';
import { BackstagePlugin } from '@backstage/core-plugin-api';
import { CompoundEntityRef } from '@backstage/catalog-model';
import { Config } from '@backstage/config';
import { CSSProperties } from '@material-ui/styles/withStyles';
import { DiscoveryApi } from '@backstage/core-plugin-api';
import { Entity } from '@backstage/catalog-model';
import { EntityOwnerPickerProps } from '@backstage/plugin-catalog-react';
import { FetchApi } from '@backstage/core-plugin-api';
import { IdentityApi } from '@backstage/core-plugin-api';
import { JSX as JSX_2 } from 'react';
import { PropsWithChildren } from 'react';
import { default as React_2 } from 'react';
import { ReactNode } from 'react';
import { ResultHighlight } from '@backstage/plugin-search-common';
import { RouteRef } from '@backstage/core-plugin-api';
import { SearchResultListItemExtensionProps } from '@backstage/plugin-search-react';
import { SyncResult as SyncResult_2 } from '@backstage/plugin-techdocs-react';
import { TableColumn } from '@backstage/core-components';
import { TableOptions } from '@backstage/core-components';
import { TableProps } from '@backstage/core-components';
import { TechDocsApi as TechDocsApi_2 } from '@backstage/plugin-techdocs-react';
import { TechDocsEntityMetadata as TechDocsEntityMetadata_2 } from '@backstage/plugin-techdocs-react';
import { TechDocsMetadata as TechDocsMetadata_2 } from '@backstage/plugin-techdocs-react';
import { TechDocsStorageApi as TechDocsStorageApi_2 } from '@backstage/plugin-techdocs-react';
import { ThemeOptions } from '@material-ui/core/styles';
import { ToolbarProps } from '@material-ui/core/Toolbar';
import { UserListFilterKind } from '@backstage/plugin-catalog-react';

// @public
export type ContentStateTypes =
  /** There is nothing to display but a loading indicator */
  | 'CHECKING'
  /** There is no content yet -> present a full screen loading page */
  | 'INITIAL_BUILD'
  /** There is content, but the backend is about to update it */
  | 'CONTENT_STALE_REFRESHING'
  /** There is content, but after a reload, the content will be different */
  | 'CONTENT_STALE_READY'
  /** There is content, the backend tried to update it, but failed */
  | 'CONTENT_STALE_ERROR'
  /** There is nothing to see but a "not found" page. Is also shown on page load errors */
  | 'CONTENT_NOT_FOUND'
  /** There is only the latest and greatest content */
  | 'CONTENT_FRESH';

// @public
export const DefaultTechDocsHome: (
  props: TechDocsIndexPageProps,
) => React_2.JSX.Element;

// @public @deprecated
export type DefaultTechDocsHomeProps = TechDocsIndexPageProps;

// @public
export const DocsCardGrid: (
  props: DocsCardGridProps,
) => React_2.JSX.Element | null;

// @public
export type DocsCardGridProps = {
  entities: Entity[] | undefined;
};

// @public
export type DocsGroupConfig = {
  title: React_2.ReactNode;
  filterPredicate: ((entity: Entity) => boolean) | string;
};

// @public
export const DocsTable: {
  (props: DocsTableProps): React_2.JSX.Element | null;
  columns: {
    createTitleColumn(
      options?:
        | {
            hidden?: boolean | undefined;
          }
        | undefined,
    ): TableColumn<DocsTableRow>;
    createNameColumn(): TableColumn<DocsTableRow>;
    createOwnerColumn(): TableColumn<DocsTableRow>;
    createKindColumn(): TableColumn<DocsTableRow>;
    createTypeColumn(): TableColumn<DocsTableRow>;
  };
  actions: {
    createCopyDocsUrlAction(copyToClipboard: Function): (row: DocsTableRow) => {
      icon: () => React_2.JSX.Element;
      tooltip: string;
      onClick: () => any;
    };
    createStarEntityAction(
      isStarredEntity: Function,
      toggleStarredEntity: Function,
    ): (row: DocsTableRow) => {
      cellStyle: {
        paddingLeft: string;
      };
      icon: () => React_2.JSX.Element;
      tooltip: string;
      onClick: () => any;
    };
  };
};

// @public
export type DocsTableProps = {
  entities: Entity[] | undefined;
  title?: string | undefined;
  loading?: boolean | undefined;
  columns?: TableColumn<DocsTableRow>[];
  actions?: TableProps<DocsTableRow>['actions'];
  options?: TableOptions<DocsTableRow>;
};

// @public
export type DocsTableRow = {
  entity: Entity;
  resolved: {
    docsUrl: string;
    ownedByRelationsTitle: string;
    ownedByRelations: CompoundEntityRef[];
  };
};

// @public
export const EmbeddedDocsRouter: (
  props: PropsWithChildren<{}>,
) => React_2.JSX.Element;

// @public
export const EntityListDocsGrid: (
  props: EntityListDocsGridPageProps,
) => React_2.JSX.Element;

// @public
export type EntityListDocsGridPageProps = {
  groups?: DocsGroupConfig[];
};

// @public
export const EntityListDocsTable: {
  (props: EntityListDocsTableProps): React_2.JSX.Element;
  columns: {
    createTitleColumn(
      options?:
        | {
            hidden?: boolean | undefined;
          }
        | undefined,
    ): TableColumn<DocsTableRow>;
    createNameColumn(): TableColumn<DocsTableRow>;
    createOwnerColumn(): TableColumn<DocsTableRow>;
    createKindColumn(): TableColumn<DocsTableRow>;
    createTypeColumn(): TableColumn<DocsTableRow>;
  };
  actions: {
    createCopyDocsUrlAction(copyToClipboard: Function): (row: DocsTableRow) => {
      icon: () => React_2.JSX.Element;
      tooltip: string;
      onClick: () => any;
    };
    createStarEntityAction(
      isStarredEntity: Function,
      toggleStarredEntity: Function,
    ): (row: DocsTableRow) => {
      cellStyle: {
        paddingLeft: string;
      };
      icon: () => React_2.JSX.Element;
      tooltip: string;
      onClick: () => any;
    };
  };
};

// @public
export type EntityListDocsTableProps = {
  columns?: TableColumn<DocsTableRow>[];
  actions?: TableProps<DocsTableRow>['actions'];
  options?: TableOptions<DocsTableRow>;
};

// @public
export const EntityTechdocsContent: (props: {
  children?: ReactNode;
}) => JSX_2.Element;

// @public
export const isTechDocsAvailable: (entity: Entity) => boolean;

// @public
export interface PanelConfig {
  // (undocumented)
  description: string;
  // (undocumented)
  filterPredicate: ((entity: Entity) => boolean) | string;
  // (undocumented)
  panelCSS?: CSSProperties;
  // (undocumented)
  panelType: PanelType;
  // (undocumented)
  title: string;
}

// @public
export type PanelType = 'DocsCardGrid' | 'DocsTable';

// @public @deprecated
export const Reader: (
  props: TechDocsReaderPageContentProps,
) => React_2.JSX.Element;

// @public
export type ReaderState = {
  state: ContentStateTypes;
  path: string;
  contentReload: () => void;
  content?: string;
  contentErrorMessage?: string;
  syncErrorMessage?: string;
  buildLog: string[];
};

// @public
export const Router: () => React_2.JSX.Element;

// @public @deprecated
export type SyncResult = 'cached' | 'updated';

// @public
export interface TabConfig {
  // (undocumented)
  label: string;
  // (undocumented)
  panels: PanelConfig[];
}

// @public
export type TabsConfig = TabConfig[];

// @public @deprecated
export interface TechDocsApi {
  // (undocumented)
  getApiOrigin(): Promise<string>;
  // (undocumented)
  getEntityMetadata(
    entityId: CompoundEntityRef,
  ): Promise<TechDocsEntityMetadata_2>;
  // (undocumented)
  getTechDocsMetadata(entityId: CompoundEntityRef): Promise<TechDocsMetadata_2>;
}

// @public @deprecated
export const techdocsApiRef: ApiRef<TechDocsApi>;

// @public
export class TechDocsClient implements TechDocsApi_2 {
  constructor(options: {
    configApi: Config;
    discoveryApi: DiscoveryApi;
    fetchApi: FetchApi;
  });
  // (undocumented)
  configApi: Config;
  // (undocumented)
  discoveryApi: DiscoveryApi;
  // (undocumented)
  getApiOrigin(): Promise<string>;
  // (undocumented)
  getCookie(): Promise<{
    expiresAt: string;
  }>;
  getEntityMetadata(
    entityId: CompoundEntityRef,
  ): Promise<TechDocsEntityMetadata_2>;
  getTechDocsMetadata(entityId: CompoundEntityRef): Promise<TechDocsMetadata_2>;
}

// @public
export const TechDocsCustomHome: (
  props: TechDocsCustomHomeProps,
) => JSX_2.Element;

// @public
export type TechDocsCustomHomeProps = {
  tabsConfig: TabsConfig;
};

// @public @deprecated (undocumented)
export type TechDocsEntityMetadata = TechDocsEntityMetadata_2;

// @public
export const TechDocsIndexPage: (
  props: TechDocsIndexPageProps,
) => JSX_2.Element;

// @public
export type TechDocsIndexPageProps = {
  initialFilter?: UserListFilterKind;
  columns?: TableColumn<DocsTableRow>[];
  actions?: TableProps<DocsTableRow>['actions'];
  ownerPickerMode?: EntityOwnerPickerProps['mode'];
};

// @public @deprecated (undocumented)
export type TechDocsMetadata = TechDocsMetadata_2;

// @public
export const TechdocsPage: () => JSX_2.Element;

// @public
export const TechDocsPageWrapper: (
  props: TechDocsPageWrapperProps,
) => React_2.JSX.Element;

// @public
export type TechDocsPageWrapperProps = {
  children?: React_2.ReactNode;
};

// @public
export const TechDocsPicker: () => null;

// @public
const techdocsPlugin: BackstagePlugin<
  {
    root: RouteRef<undefined>;
    docRoot: RouteRef<{
      name: string;
      kind: string;
      namespace: string;
    }>;
    entityContent: RouteRef<undefined>;
  },
  {}
>;
export { techdocsPlugin as plugin };
export { techdocsPlugin };

// @public
export const TechDocsReaderLayout: (
  props: TechDocsReaderLayoutProps,
) => React_2.JSX.Element;

// @public
export type TechDocsReaderLayoutProps = {
  withHeader?: boolean;
  withSearch?: boolean;
};

// @public
export const TechDocsReaderPage: (
  props: TechDocsReaderPageProps,
) => JSX_2.Element;

// @public
export const TechDocsReaderPageContent: (
  props: TechDocsReaderPageContentProps,
) => React_2.JSX.Element;

// @public
export type TechDocsReaderPageContentProps = {
  entityRef?: CompoundEntityRef;
  withSearch?: boolean;
  searchResultUrlMapper?: (url: string) => string;
  onReady?: () => void;
};

// @public
export const TechDocsReaderPageHeader: (
  props: TechDocsReaderPageHeaderProps,
) => React_2.JSX.Element | null;

// @public @deprecated
export type TechDocsReaderPageHeaderProps = PropsWithChildren<{
  entityRef?: CompoundEntityRef;
  entityMetadata?: TechDocsEntityMetadata_2;
  techDocsMetadata?: TechDocsMetadata_2;
}>;

// @public (undocumented)
export type TechDocsReaderPageProps = {
  entityRef?: CompoundEntityRef;
  children?: TechDocsReaderPageRenderFunction | ReactNode;
  overrideThemeOptions?: Partial<ThemeOptions>;
};

// @public
export type TechDocsReaderPageRenderFunction = (options: {
  techdocsMetadataValue?: TechDocsMetadata_2 | undefined;
  entityMetadataValue?: TechDocsEntityMetadata_2 | undefined;
  entityRef: CompoundEntityRef;
  onReady?: () => void;
}) => JSX.Element;

// @public
export const TechDocsReaderPageSubheader: (props: {
  toolbarProps?: ToolbarProps;
}) => React_2.JSX.Element | null;

// @public
export const TechDocsReaderProvider: (
  props: TechDocsReaderProviderProps,
) => React_2.JSX.Element;

// @public
export type TechDocsReaderProviderProps = {
  children: TechDocsReaderProviderRenderFunction | ReactNode;
};

// @public
export type TechDocsReaderProviderRenderFunction = (
  value: ReaderState,
) => JSX.Element;

// @public
export const TechDocsSearch: (
  props: TechDocsSearchProps,
) => React_2.JSX.Element;

// @public
export type TechDocsSearchProps = {
  entityId: CompoundEntityRef;
  entityTitle?: string;
  debounceTime?: number;
  searchResultUrlMapper?: (url: string) => string;
};

// @public
export const TechDocsSearchResultListItem: (
  props: SearchResultListItemExtensionProps<TechDocsSearchResultListItemProps>,
) => JSX.Element | null;

// @public
export type TechDocsSearchResultListItemProps = {
  icon?: ReactNode | ((result: any) => ReactNode);
  result?: any;
  highlight?: ResultHighlight;
  rank?: number;
  lineClamp?: number;
  asListItem?: boolean;
  asLink?: boolean;
  title?: string;
};

// @public @deprecated
export interface TechDocsStorageApi {
  // (undocumented)
  getApiOrigin(): Promise<string>;
  // (undocumented)
  getBaseUrl(
    oldBaseUrl: string,
    entityId: CompoundEntityRef,
    path: string,
  ): Promise<string>;
  // (undocumented)
  getBuilder(): Promise<string>;
  // (undocumented)
  getEntityDocs(entityId: CompoundEntityRef, path: string): Promise<string>;
  // (undocumented)
  getStorageUrl(): Promise<string>;
  // (undocumented)
  syncEntityDocs(
    entityId: CompoundEntityRef,
    logHandler?: (line: string) => void,
  ): Promise<SyncResult>;
}

// @public @deprecated
export const techdocsStorageApiRef: ApiRef<TechDocsStorageApi>;

// @public
export class TechDocsStorageClient implements TechDocsStorageApi_2 {
  constructor(options: {
    configApi: Config;
    discoveryApi: DiscoveryApi;
    fetchApi: FetchApi;
    identityApi?: IdentityApi;
  });
  // (undocumented)
  configApi: Config;
  // (undocumented)
  discoveryApi: DiscoveryApi;
  // (undocumented)
  getApiOrigin(): Promise<string>;
  // (undocumented)
  getBaseUrl(
    oldBaseUrl: string,
    entityId: CompoundEntityRef,
    path: string,
  ): Promise<string>;
  // (undocumented)
  getBuilder(): Promise<string>;
  getEntityDocs(entityId: CompoundEntityRef, path: string): Promise<string>;
  // (undocumented)
  getStorageUrl(): Promise<string>;
  syncEntityDocs(
    entityId: CompoundEntityRef,
    logHandler?: (line: string) => void,
  ): Promise<SyncResult_2>;
}
```
